# White Paper 9 - Database, Event Sourcing, and Service APIs

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE should use event-sourced state transitions with projected read models. The event log is the audit trail. Property sheets are the current state surface. Service APIs pass packets that can be replayed and inspected.

## Storage Strategy

The storage layer should separate canonical events from query projections.

| Store | Purpose |
| --- | --- |
| Event log | Canonical history of committed changes. |
| Property sheet store | Current authoritative state. |
| Projection tables | Fast read models for locations, inventory, timelines, and branches. |
| Corpus graph | Source claims, authority, concepts, and conflicts. |
| Replay store | Context packets, seeds, model versions, and verifier results. |

## SQL Sketch

```sql
CREATE TABLE event_log (
  event_log_id BIGSERIAL PRIMARY KEY,
  event_id TEXT NOT NULL,
  partition_id TEXT NOT NULL,
  actor_id TEXT,
  causation_id TEXT NOT NULL,
  event_type TEXT NOT NULL,
  tick BIGINT NOT NULL,
  payload JSONB NOT NULL,
  read_versions JSONB NOT NULL,
  write_versions JSONB NOT NULL,
  source_version_set TEXT NOT NULL,
  replay_seed TEXT,
  committed_at TIMESTAMPTZ NOT NULL DEFAULT now()
);

CREATE TABLE object_projection (
  object_id TEXT PRIMARY KEY,
  object_type TEXT NOT NULL,
  current_location_id TEXT,
  current_container_id TEXT,
  owner_id TEXT,
  quantity NUMERIC,
  state JSONB NOT NULL,
  version INTEGER NOT NULL
);

CREATE TABLE location_projection (
  location_id TEXT PRIMARY KEY,
  parent_location_id TEXT,
  partition_id TEXT NOT NULL,
  exits JSONB NOT NULL,
  conditions JSONB NOT NULL,
  contained_entities JSONB NOT NULL,
  version INTEGER NOT NULL
);
```

## API Contract Style

AGE internal APIs should be typed packet contracts. A service call should say what it reads, what it proposes, what it commits, and what it returns.

| API | Owner | Purpose |
| --- | --- | --- |
| InputCoordinator.classify | Input Coordinator | Route raw request to mode. |
| ScopeResolver.resolve | Scope Resolver | Identify partitions and visible state. |
| StateAssembler.build_context | State Assembler | Create LLM context packet. |
| RulesService.resolve_action | Rules Service | Produce deterministic resolution packet. |
| CAL.query | CAL | Return corpus answer packet. |
| StateMutationEngine.commit | State Mutation Engine | Apply validated mutations. |
| OutputVerifier.verify | Output Verifier | Compare visible prose to committed state. |

## Commit API

```yaml
api: StateMutationEngine.commit
request:
  mutation_batch_id: batch_000184
  causation_id: req_000184
  partition_id: partition_locus_blackstone_tavern
  read_versions:
    obj_iron_key: 7
    inv_npc_bartender_orren: 17
    inv_pc_adel: 41
  mutations:
    - type: inventory_transfer
      object_id: obj_iron_key
      from_container: inv_npc_bartender_orren
      to_container: inv_pc_adel
  validation_evidence:
    rules_packet_id: rules_000184
    scope_packet_id: scope_000184
response:
  status: committed
  write_versions:
    obj_iron_key: 8
    inv_npc_bartender_orren: 18
    inv_pc_adel: 42
  event_log_ids: [884512]
```

## Failure Modes

A packet API fails usefully when it returns structured error. `version_conflict`, `missing_authority`, `invalid_location`, `hidden_field_access`, and `rule_conflict` are better than a generated apology. Each error should be recoverable by the coordinator or visible as a clear response to the user.

## Acceptance Test

A database test should execute concurrent commits for the same object, verify only one succeeds without conflict policy, then rerun with conflict policy enabled and verify the conflict becomes a deterministic game resolution.
