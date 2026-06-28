# White Paper 5 - AGEScript, Event Generators, and Authored Consequence

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGEScript is the authored consequence layer. It gives authors a way to define scenes, spotlights, aggregation, outcomes, mutations, and narrative hooks without writing every possible branch. Event Generators supply state-filtered procedural events that respect partition scope and scenario authority.

## Why Text Branching Fails

Flow-centric branching works for solo choices. It fails for troupe play because combinations multiply. If five players each choose one of three actions, a direct branch tree has 243 combinations. Most combinations are not narratively meaningful. AGE therefore collapses inputs into a bounded set of outcomes through AGEScript resolution.

![AGEScript pipeline](assets/diagrams/agescript_pipeline.png)

## AGEScript Scene Record

AGEScript source should remain readable by authors, but the runtime should execute compiled JSON. The authoring layer may use YAML-like syntax.

```yaml
scene_id: harbor_gate_ambush
plot_family: pursuit_and_escape
phase: crisis
location_id: locus_sunken_harbor_gate
duration:
  spotlight_count: 4
  tick_policy: scene_minutes
anchors:
  actors: [npc_gate_captain, npc_smuggler_child]
  objects: [obj_gate_chain, obj_signal_lantern]
  flags: [harbor_alert_level, smuggler_route_known]
spotlights:
  - spotlight_id: group_response_01
    input_mode: simultaneous
    prompt: "The gate chain rises and the patrol turns. What does each character do?"
    valid_intents:
      - fight
      - hide
      - negotiate
      - cut_chain
      - protect_child
aggregation:
  compatible_sets:
    - [hide, protect_child]
    - [fight, cut_chain]
  competing_sets:
    - [negotiate, fight]
  conflict_policy: scene_rule_then_occ
outcomes:
  chain_cut_escape:
    condition: "count(cut_chain) >= 1 AND count(fight) >= 1"
    state_mutations:
      - set_object_state: obj_gate_chain = cut
      - set_flag: harbor_alert_level +30
      - set_location: troupe = locus_harbor_backwater
    narrative_hooks:
      - "the chain snaps under cover of violence"
      - "the patrol remembers the party's faces"
```

## Compilation

The AGEScript compiler should perform three jobs.

1. Syntax validation: required fields, valid references, valid operators, valid mutation forms.
2. Authority validation: referenced actors, objects, flags, and locations exist or are declared as created.
3. Runtime compilation: produce a deterministic JSON artifact with normalized IDs, resolved references, and static checks.

```yaml
compiled_scene:
  artifact_id: agec_harbor_gate_ambush_v003
  source_scene_id: harbor_gate_ambush
  source_version: 3
  static_reads:
    actor_ids: [npc_gate_captain, npc_smuggler_child]
    object_ids: [obj_gate_chain, obj_signal_lantern]
    flag_ids: [harbor_alert_level, smuggler_route_known]
  mutation_forms:
    - set_object_state
    - set_flag
    - set_location
  deterministic_seed_basis: campaign_seed + scene_id + spotlight_id
```

## Event Generator Tables

Event Generators are not ordinary random tables. They are state-filtered event sources. Each entry has prerequisites, weights, effects, and narrative seeds. The generator must filter entries before rolling or selection.

```yaml
event_table:
  table_id: table_coastal_horror_minor_events
  partition_scope: locus_or_scene
  inherits_from: table_coastal_weather_base
  entries:
    - entry_id: gulls_fall_silent
      weight: 8
      prerequisites:
        - time.light_level in [dusk, night]
        - flag.horror_pressure >= 2
      effects:
        - set_flag: local_unease +1
      narrative_seeds:
        - "gulls stop crying all at once"
    - entry_id: freshwater_burns_skin
      weight: 3
      prerequisites:
        - actor.transformation_track >= 3
        - location.has_freshwater == true
      effects:
        - increment_track: self_preservation_stress +1
      narrative_seeds:
        - "freshwater feels like lye against altered skin"
```

## State Filtering Algorithm

The Event Generator should operate in this order.

1. Load table and inherited parent tables.
2. Remove entries outside active partition scope.
3. Remove entries whose prerequisites fail.
4. Adjust weights using active flags and concern overlays.
5. Roll or select using deterministic seed.
6. Produce a candidate event packet.
7. Validate effects through the Consistency Arbiter.
8. Commit event effects before prose rendering.

## Failure Modes

The most common failure is flavorful but invalid event selection. For example, a freshwater transformation event should not trigger in a dry mountain scene merely because horror tone is high. The table entry must require the location condition. The second common failure is hidden event leakage. If cult observers move off-screen, the player should not be told unless visibility rules permit it.

## Acceptance Test

A test scene should run the same event table in three locations: sea cave, freshwater bridge, and inland tavern. The engine should select different eligible events because state differs. If the freshwater event appears in the tavern without freshwater state, the generator fails.
