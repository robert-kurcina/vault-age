# White Paper 7 - Multiplayer Branching and Troupe Isolation

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE multiplayer should use simultaneous input and controlled merge semantics rather than strict rotation or unconstrained improvisation. Troupe-local branches are isolated until bridge policies export redacted ripple events.

## Problem

A role-playing troupe does not need every player to act in a rigid sequence for every beat. It also cannot allow all players to freely rewrite the same state. The runtime must distinguish compatible actions, competing actions, and conflicting actions.

![Multiplayer merge flow](assets/diagrams/multiplayer_merge.png)

## Input Classes

| Class | Meaning | Runtime handling |
| --- | --- | --- |
| Compatible | Actions can all be true. | Merge into one outcome. |
| Competing | Actions pursue different priorities but do not target the same state. | Order by scene rule, role, initiative, or position. |
| Conflicting | Actions attempt incompatible writes. | Use OCC and conflict policy. |
| Private | Action is visible only to one player or subset. | Store in private branch state. |
| Out-of-world | Player instruction, question, or command. | Route outside scene resolution. |

## Branch Record

```yaml
branch_record:
  branch_id: branch_troupe_blackstone_01_scene_22
  troupe_id: troupe_blackstone_01
  parent_partition: partition_locus_blackstone_tavern
  start_tick: 10480
  current_tick: 10489
  active_players: [player_adel, player_borin, player_cassia]
  visibility_model:
    shared: [location_state, visible_actors, visible_objects]
    private_by_player:
      player_adel: [secret_note_seen]
      player_borin: []
  commit_policy:
    compatible_inputs: merge
    competing_inputs: spotlight_rule
    conflicting_inputs: occ_then_game_resolution
```

## Conflict Resolution

The engine should convert plausible simultaneous conflicts into game procedures. If two players grab the same relic, that is not merely a database exception. It is a scene moment. If one player tries to flee while another blocks the door, the conflict may become an opposed test or a social choice. If the conflict is not fictionally plausible, the engine can reject one input and ask for clarification.

## Cross-Troupe Influence

Troupe A can influence Troupe B only through shared partition mechanisms. Direct branch merging is allowed only when time, location, and visibility support it. Otherwise the world partition receives a ripple event and later exposes a redacted effect.

```yaml
ripple_event:
  ripple_id: ripple_bridge_destroyed_001
  source_branch: branch_troupe_a_bridge_scene
  source_partition: partition_locus_west_bridge
  target_partition: partition_realm_veridian
  public_summary: "The west bridge has fallen."
  hidden_causes:
    - pc_adel_cut_support_rope
    - npc_spy_witnessed_event
  downstream_policy:
    expose_as: rumor_or_travel_obstacle
    earliest_tick: 12040
```

## Failure Modes

The dangerous failure is false shared reality. If Troupe A and Troupe B both believe they uniquely possess the same artifact, the artifact state has split without policy. AGE must either isolate those branches intentionally, create alternate instances explicitly, or prevent the contradiction through OCC and bridge rules.

## Acceptance Test

Run two troupes in the same realm. Let one group unlock a tunnel and leave a marker. Let another group approach the tunnel later. The result should depend on time, location, visibility, and bridge policy. The second group may see the open tunnel, a rumor, a changed guard route, or nothing. The result should not be arbitrary prose.
