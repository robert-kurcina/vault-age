# Specification 2 - AGEScript Reference Sketch

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.


## Purpose

This file gives a compact AGEScript reference for implementation planning.

## Required Blocks

| Block | Required? | Purpose |
| --- | --- | --- |
| scene_id | yes | Stable scene identity. |
| plot_family | optional | Story family or plot archetype. |
| phase | yes | Narrative phase such as setup, pressure, crisis, aftermath. |
| location_id | yes | Location Sheet anchor. |
| duration | yes | Spotlight count and TickPolicy. |
| anchors | yes | State loaded for resolution and rendering. |
| spotlights | yes | Player input windows. |
| aggregation | optional | Merge and conflict logic. |
| outcomes | yes | Bounded outcome set. |

## Operators

```yaml
conditions:
  count(choice_id) >= integer
  flag(flag_id) == value
  actor(actor_id).field >= value
  object(object_id).state == value
  any(player.intent == intent_id)
  all(required_flags_present)
```

## Mutation Forms

```yaml
state_mutations:
  - set_flag: flag_id = value
  - increment_track: actor_id.track_id + integer
  - transfer_object: object_id -> container_id
  - set_location: actor_or_troupe_id = location_id
  - create_event: event_id
  - add_relationship_edge: from_id -> to_id
```

## Compilation Requirements

The compiler must reject missing anchors, unknown locations, unknown mutation forms, unresolved object IDs, impossible outcome fall-through, and hidden-field references not permitted by role.
