# White Paper 11 - Worked Dagon-Style Runtime Trace

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

The Dagon-style scenario is useful because it forces AGE to coordinate time, location, transformation, hidden observers, environmental effects, carried objects, and final scoring. This paper converts that kind of narrative sequence into runtime records.

## Scenario Shape

The player begins on a coastal route, moves through a sea cave, experiences transformation pressure, crosses toward freshwater and elevation, interacts with hidden cult pressure, and receives final scores. The exact literary surface is less important than the technical stressors.

## Initial State Snapshot

```yaml
snapshot_id: snapshot_dagon_start
world_tick: 200
active_partition: partition_locus_boothbay_shoreline
actor_sheets:
  - actor_id: pc_marsh_reporter
    location_id: locus_boothbay_strand
    inventory_id: inv_pc_marsh_reporter
    state_tracks:
      exhaustion: 0
      transformation: 1
      horror: 1
object_sheets:
  - object_id: obj_crystalline_vertebra_fragment
    location_id: locus_boothbay_devils_throat_cave
    object_type: evidence_macguffin
location_sheets:
  - location_id: locus_boothbay_devils_throat_cave
    conditions:
      saltwater: true
      freshwater: false
      tide_sensitive: true
  - location_id: locus_boothbay_maiden_tear_footbridge
    conditions:
      freshwater: true
      elevation: ridge
hidden_events:
  - event_cult_observer_moves
```

## Turn Trace

| Turn | Player action | Runtime state operation | Visible result |
| --- | --- | --- | --- |
| 1 | Searches strand. | Reads shoreline Location Sheet and event table. | Finds signs of unnatural tide. |
| 2 | Enters cave. | Commits TransitionPacket to cave; advances ticks. | Cave description uses saltwater conditions. |
| 3 | Takes fragment. | Commits object transfer from location to inventory. | Fragment is now carried. |
| 4 | Studies marks. | CAL retrieves scenario lore and hidden constraints. | Reveals partial truth, not cult observer. |
| 5 | Leaves cave for ridge. | Commits route travel and tide event. | Time and exhaustion update. |
| 6 | Crosses footbridge. | Checks freshwater condition against transformation track. | Transformation stress increases. |
| 7 | Looks back. | Visibility check may reveal observer if conditions met. | Hidden actor remains hidden or becomes clue. |
| 8 | Chooses final action. | Computes final score from committed tracks. | Final assessment follows state. |

## Transition Example

```yaml
transition_packet_id: trans_dagon_006
actor_id: pc_marsh_reporter
from_location: locus_boothbay_devils_throat_cave
to_location: locus_boothbay_maiden_tear_footbridge
route_id: route_cave_ridge_footbridge
start_tick: 218
end_tick: 242
crossed_events:
  - event_tide_turning
  - event_cult_observer_moves
state_effects:
  - set_location: pc_marsh_reporter = locus_boothbay_maiden_tear_footbridge
  - increment_track: pc_marsh_reporter.exhaustion +1
  - set_flag: pc_marsh_reporter.silver_tracery_visible = true
```

## Final Score Packet

```yaml
score_packet:
  score_id: score_dagon_final_001
  actor_id: pc_marsh_reporter
  scoring_basis:
    truth_preserved:
      from_flags: [evidence_collected, cult_pattern_understood]
      value: 1.7
    self_preserved:
      from_tracks: [transformation, exhaustion, horror]
      value: 2.4
    horror_contained:
      from_events: [observer_not_followed_to_town, fragment_secured]
      value: 1.3
  visible_summary_allowed: true
```

## Why This Matters

The Dagon-style trace proves whether AGE can preserve a long causal chain. If the final score is merely inferred from prose tone, AGE has failed. If the final score is computed from committed state, AGE has become a game engine.
