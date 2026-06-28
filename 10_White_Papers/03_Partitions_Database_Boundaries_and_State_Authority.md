# White Paper 3 - Partitions, Database Boundaries, and State Authority

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE partitioning is a state-authority system. It uses spatial, narrative, temporal, concern, and role facets to decide what state is in scope, who can mutate it, what can cross boundaries, and how local play affects wider worlds. Partitioning can scope retrieval, but it is not retrieval. Retrieval consumes model context; partition authority commits state.

## Target Problem

A persistent game world cannot place the entire world in every prompt. It also cannot retrieve a handful of documents and call that state. The system needs a way to bind context, ownership, event routing, and commit rules to a specific scope.

A player in one tavern scene needs local actors, objects, exits, immediate rules, and hidden constraints. The same player does not need every kingdom's treasury, every hidden faction plan, or another troupe's private discoveries. However, if the local action creates a realm-level consequence, that consequence must travel upward in a controlled form.

## Partition Facets

A DomainPartition has facets. Each facet answers a different question.

| Facet | Question answered | Example |
| --- | --- | --- |
| Spatial | Where is the state physically or geographically? | World, Region, Realm, Locus, Submap. |
| Narrative | What story scale is active? | Epic, Arc, Chapter, Act, Scene, Spotlight. |
| Temporal | What tick policy applies? | Seconds, minutes, days, months. |
| Concern | Which cross-cutting subsystem constrains this state? | Economy, Law, Faction, Ecology, Weather. |
| Role | Which actor or service may read or write? | Player, Referee, Rules Service, Author. |

![Partition topology](assets/diagrams/partition_topology.png)

## Partition Record

```yaml
partition_id: partition_realm_veridian
partition_type: DomainPartition
facets:
  spatial: realm
  narrative: chapter
  temporal: days
  concerns: [economy, law, faction]
parent_partition: partition_region_sondgara_archipelago
child_partitions:
  - partition_locus_blackstone_pass
  - partition_locus_sunken_harbor
state_ownership:
  owns_sheets_matching:
    - location.parent_location == realm_veridian
    - faction.home_realm == realm_veridian
read_policy:
  local_troupe: visible_projection_only
  referee: full_partition
  world_scheduler: summary_projection
write_policy:
  local_scene: no_direct_write
  event_scheduler: allow_validated_ripple
  referee: allow_with_audit
bridge_policy:
  upstream: aggregate_and_redact
  downstream: inject_as_event_or_condition
  cross_troupe: ripple_only
version: 11
```

## Partition Boundaries Are Stronger Than Retrieval

Retrieval can surface a rule, a location description, or a prior event, but retrieval consumes input context and is inefficient as the ordinary state mechanism. Retrieval cannot decide whether material is authorized to change state. A partition can. This distinction matters when two troupes overlap, when a player has private knowledge, when a hidden cult observer is present, or when a realm-level faction war changes a local road.

The partition should produce a scoped context packet. Retrieval should operate inside that scope.

```yaml
context_scope:
  active_partition: partition_locus_blackstone_tavern
  allowed_sheet_families: [ActorSheet, LocationSheet, ObjectSheet, EventSheet]
  allowed_corpus_authority: [canonical_rule, scenario_rule, referee_ruling]
  denied_fields:
    - ActorSheet.hidden_traits
    - EventSheet.hidden_prerequisites
    - BranchRecord.private_troupe_notes
  max_temporal_distance_ticks: 120
  retrieval_strategy:
    rules: exact_authority_first
    lore: local_then_parent
    examples: same_scene_type_only
```

## Database Partitioning

The logical DomainPartition does not require one physical database per partition, but the physical storage should preserve partition keys. Partition keys allow efficient read models, conflict isolation, and audit trails.

```sql
CREATE TABLE partitions (
  partition_id TEXT PRIMARY KEY,
  parent_partition_id TEXT,
  facets JSONB NOT NULL,
  tick_policy JSONB NOT NULL,
  bridge_policy JSONB NOT NULL,
  validation_policy JSONB NOT NULL,
  version INTEGER NOT NULL
);

CREATE TABLE state_events (
  event_log_id BIGSERIAL PRIMARY KEY,
  partition_id TEXT NOT NULL,
  causation_id TEXT NOT NULL,
  actor_id TEXT,
  event_type TEXT NOT NULL,
  tick BIGINT NOT NULL,
  payload JSONB NOT NULL,
  source_versions JSONB NOT NULL,
  committed_at TIMESTAMPTZ NOT NULL DEFAULT now()
);

CREATE INDEX state_events_partition_tick
ON state_events(partition_id, tick);
```

## Bridge Policies

Bridge policies control cross-partition movement.

| Bridge type | Meaning | Example |
| --- | --- | --- |
| Local | Event remains inside the active partition. | A cup breaks in a tavern. |
| Upstream ripple | Local event becomes a summary effect in a parent. | Tavern murder increases city watch alert. |
| Downstream injection | Parent event becomes local condition. | War causes mercenaries at the bridge. |
| Cross-troupe redaction | One troupe affects another through public consequence only. | Rumor spreads that the tunnel is open. |
| Direct merge | Two branches combine because proximity and time allow it. | Two parties enter the same room together. |

## Failure Modes

Partition failure usually appears as over-sharing or under-sharing. Over-sharing leaks hidden information or allows local play to rewrite global state. Under-sharing makes the world feel dead because higher-level events never affect local scenes. The bridge policy must be explicit enough to prevent both failures.

## Acceptance Test

A partition test should run two troupes in the same realm. Troupe A destroys a bridge at tick 100. Troupe B begins at tick 95 on the other side of the realm. The test should verify whether the bridge event is invisible, foreshadowed, encountered, or impossible depending on travel time, causal window, and bridge policy. The engine should not improvise a single answer for all cases.
