# Specification 1 - Property Sheet and Runtime Packet Reference

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



## Definitions Before Use

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE uses generated prose, but generated prose is not authoritative by itself. The engine keeps truth in structured state, validates proposed changes, commits approved changes, and then renders prose from the committed state.

A large language model [LLM] is a statistical text model that can generate, transform, classify, and summarize language. AGE may use an LLM to render scene prose, dialogue, summaries, classifications, and possible state deltas. AGE does not permit an LLM to directly advance time, move objects, create inventory, resolve conflicts, or alter canonical facts.

A Large Model System [LMS] is the total model-support system around one or more LLMs. An LMS may include retrieval, embedding search, graph search, tool calls, routing, memory, adapters, prompts, and audit controls. The Large Model System Graph [LMS-Graph] is the AGE corpus graph that records sources, concepts, claims, versions, examples, authority tiers, dependencies, and conflicts.

The Corpus Arbitration Layer [CAL] is the AGE service that answers against LMS-Graph. CAL retrieves candidate evidence, weighs authority, exposes conflicts, preserves source provenance, and identifies when a human ruling is required.

A DomainPartition is the principal AGE runtime partition. It owns a bounded portion of world state, narrative jurisdiction, time policy, bridge policy, event routing, and commit authority. A DomainPartition derives from an AbstractPartition contract. Human-facing labels may use forms such as ConcernPartition:Economy or SpatialPartition:Locus; implementation code may use typed fields rather than literal colon names.

A property sheet is a structured state record for one entity or runtime object. A property sheet records identity, scope, owner, version, visible fields, hidden fields, permitted mutations, invariants, dependencies, and partition access. Actor Sheet, Location Sheet, Object Sheet, Event Sheet, Partition Sheet, and Role Sheet are property sheet families.

AGEScript is the AGE authoring language for scenes, spotlights, choices, aggregation, resolution, state mutations, and narrative hooks. AGEScript is author-readable, but it compiles into deterministic JavaScript Object Notation [JSON] artifacts for runtime execution. JSON is a machine-readable data format used here for structured runtime records. YAML Ain't Markup Language [YAML] is a human-readable data format used here for examples and authoring sketches.

Structured Query Language [SQL] is the language used in this archive for relational database sketches. A Universally Unique Identifier [UUID] is a stable identifier used in examples for records that must remain distinct across partitions, services, or clients.

Optimistic Concurrency Control [OCC] is the version-checking method used when multiple clients attempt to change the same state. A client writes against a known version. If the server version changed first, the write cannot silently overwrite the newer state. AGE then retries, rejects, or resolves the conflict through a game procedure.

Retrieval-Augmented Generation [RAG] is the practice of retrieving relevant source material and placing it into a model context. AGE may use Retrieval-Augmented Generation as a scoped, read-only aid inside the Corpus Arbitration Layer or State Assembler when structured state cannot answer directly. It should not be the ordinary partition mechanism because it consumes input context and is not efficient as a state authority. AGE partitioning is stronger than retrieval because a partition decides who owns truth, what can cross a boundary, what may be mutated, and how a change becomes authoritative.

An Application Programming Interface [API] is a defined service contract for software components. AGE internal APIs are described as request and response packets because the first implementation should make each state transition auditable.

Quality Assurance [QA] is the practice of testing and certifying whether AGE preserves state, rules, source authority, partition boundaries, and replay behavior. Semantic QA checks meaning, not only software execution.

A Minimum Viable Product [MVP] is the narrow first implementation that proves AGE's central claim before wider platform expansion. The MVP should prove state authority, partition scope, time, location, property sheets, AGEScript scenes, rules arbitration, replay, and QA in one bounded game environment.


## Purpose

This specification collects the concrete packet and property-sheet forms used by the white papers. It is intentionally implementation-facing.

## Common Property Sheet Fields

```yaml
sheet_id: string
sheet_family: ActorSheet | LocationSheet | ObjectSheet | EventSheet | PartitionSheet | RoleSheet
authority_partition: string
version: integer
created_tick: integer
updated_tick: integer
visibility:
  default: string
  hidden_fields: list[string]
mutation_policy:
  require_occ: boolean
  allowed_services: list[string]
invariants: list[string]
visible_payload: object
hidden_payload: object
```

## Common Runtime Packet Fields

```yaml
request_id: string
causation_id: string
partition_id: string
world_tick: integer
source_version_set: string
model_profile: string | null
replay_seed: string | null
read_versions: object
write_versions: object | null
verifier_status: pending | passed | failed
```

## Mutation Types

| Mutation | Required fields |
| --- | --- |
| inventory_transfer | object_id, from_container, to_container. |
| location_move | actor_id, from_location, to_location, route_id. |
| track_increment | actor_id, track_id, delta. |
| flag_set | flag_id, value, authority_partition. |
| object_state_set | object_id, state_field, value. |
| event_create | event_id, scheduled_tick, event_type, effects. |
| corpus_claim_add | claim_id, source_id, authority_tier. |

## Verifier Conditions

The Output Verifier should check these claims in visible prose:

- object moved;
- actor moved;
- time passed;
- rule resolved;
- event occurred;
- hidden fact revealed;
- resource changed;
- relationship changed;
- final score changed.

Each detected claim must map to a committed mutation, allowed visibility rule, or non-state descriptive allowance.
