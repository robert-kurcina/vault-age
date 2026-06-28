# White Paper 1 - Core Runtime and State Authority

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

The AGE runtime is a state transaction pipeline. It converts player or system input into scoped reads, validated decisions, committed state changes, and state-faithful output. The runtime's main design rule is that an LLM may propose and render, but it may not own truth.

## Problem

Generated interactive fiction commonly fails when prior prose is treated as memory. If an object is mentioned in prose, the next turn may treat it as available even when no inventory record exists. If a character is wounded, later narration may ignore the wound. If two players act at once, the model may merge their actions in a way that satisfies tone but not state. These are not merely storytelling errors. They are transaction errors.

The runtime must therefore provide explicit authority boundaries. It must decide which partition owns the action, which property sheets are read, which rules apply, which state changes are permitted, and which output claims are true.

## Architecture

![Runtime transaction sequence](assets/diagrams/transaction_sequence.png)

The runtime has seven active components.

| Component | Responsibility | Must not do |
| --- | --- | --- |
| Input Coordinator | Classifies the request and selects mode. | Commit state or invent facts. |
| Scope Resolver | Locates partition, time, location, role, and visible state. | Read the whole world when a local view is enough. |
| State Assembler | Builds the context packet for the LLM. | Dump raw database rows without visibility filtering. |
| Fiction Constructor | Renders prose and candidate deltas. | Become source of truth. |
| Consistency Arbiter | Validates candidate prose and deltas. | Hide conflicts or create canon silently. |
| State Mutation Engine | Commits approved deltas and event log records. | Use generative reasoning. |
| Output Verifier | Ensures visible output matches committed state. | Allow prose to claim uncommitted outcomes. |

## Runtime Packets

The runtime should pass packets rather than loosely structured prompt strings. A packet can be logged, replayed, diffed, and checked.

```yaml
request_packet:
  request_id: req_000184
  actor_id: pc_adel
  troupe_id: troupe_blackstone_01
  raw_text: "I take the iron key while the bartender argues."
  channel: player_action
  client_state_version: 421

scope_packet:
  request_id: req_000184
  active_partitions:
    spatial: partition_locus_blackstone_tavern
    narrative: partition_scene_tavern_brawl_01
    temporal: tick_policy_scene_minutes
    concerns: [law_local, reputation_tavern]
  current_tick: 10488
  visible_entities:
    actors: [pc_adel, npc_bartender_orren, npc_guard_pair]
    objects: [obj_iron_key, obj_bar_counter, obj_locked_back_door]
  hidden_constraints:
    - npc_guard_pair_contains_informant_do_not_reveal

mutation_packet:
  mutation_id: mut_000184_01
  mutation_type: inventory_transfer
  object_id: obj_iron_key
  from_container: inv_npc_bartender_orren
  to_container: inv_pc_adel
  preconditions:
    - obj_iron_key.version == 7
    - pc_adel.location_id == locus_blackstone_tavern_common_room
    - npc_bartender_orren.distraction_state == high
  rule_basis: rule_stealth_vs_notice
```

## Normal Execution

Normal execution is a two-phase shape: resolve first, render second. The system may call an LLM before final resolution to classify intent or draft possibilities, but the committed outcome should be resolved before final prose is returned. This avoids the common failure in which attractive prose forces the engine to accept an impossible state change.

A successful object transfer proceeds as follows.

1. The Scope Resolver reads the Actor Sheet for the acting character, Object Sheet for the target object, container sheets for both inventories, Location Sheet for the room, and relevant rule claims.
2. The resolver confirms reach, visibility, container access, and current version.
3. The rules subsystem resolves the action.
4. The Mutation Engine writes the inventory transfer, increments versions, appends an event, and emits any legal or reputation ripple.
5. The Fiction Constructor receives committed outcome hooks and renders the success.
6. The Output Verifier checks that the prose does not reveal hidden facts or claim uncommitted side effects.

## Failure Behavior

The runtime should treat failures as explicit outcomes.

| Failure | Cause | Correct behavior |
| --- | --- | --- |
| Classification ambiguity | Input could be action or out-of-character command. | Ask a clarifying question or use mode priority. |
| Missing scope | Required location or partition is not loaded. | Return a recoverable system error; do not improvise state. |
| Version conflict | Another player changed the object first. | Apply OCC conflict policy. |
| Rule conflict | CAL finds incompatible sources. | Use active authority tier or request human ruling. |
| Prose contradiction | LLM output contradicts state. | Revise or regenerate from committed hooks. |
| Hidden-info leakage | Candidate response reveals hidden state. | Remove or regenerate the response. |

## Invariants

The core runtime should enforce these invariants before it is considered usable.

- Every committed mutation has an actor, cause, rule basis or system basis, timestamp, partition, and prior version.
- Every visible response that claims a state change can be traced to a committed mutation.
- Every LLM output is attached to the context packet that produced it.
- No component except the State Mutation Engine writes canonical state.
- No troupe-local state crosses to another troupe except through a bridge policy.
- Replay with the same source versions, seeds, and deterministic policies produces the same committed state.

## Implementation Test

A first runtime acceptance test should execute 100 scripted turns in one tavern scene. The test should include object transfer, failed object transfer, hidden information, time advancement, two player inputs targeting the same object, a rules question, a location transition, and a missed event. The test passes only if final state, event log, and visible prose are consistent.
