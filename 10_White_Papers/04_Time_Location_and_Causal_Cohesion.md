# White Paper 4 - Time, Location, and Causal Cohesion

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE requires authoritative time and structured location because persistent narrative depends on causal order. The runtime must know what tick it is, where actors are, how long travel takes, what events occurred off-screen, and which events can plausibly affect which partitions.

## Tick Policies

A tick is the smallest time step used by a partition. Tick duration depends on abstraction layer. The origin branch states this directly: Spotlight operates in seconds to minutes, Scene in minutes, Locus in minutes to hours, Realm in sessions or days, Region and Arc in larger campaign spans, and Epic or World in months or years.

| Partition scale | Typical tick | Use |
| --- | --- | --- |
| Spotlight | seconds or one exchange | Immediate action and dialogue. |
| Scene | minutes | Local encounter or decision block. |
| Locus | minutes to hours | Movement through one adventure site. |
| Realm | days or sessions | Faction pressure, travel, law, resources. |
| Region | weeks or campaigns | Strategic shifts and wars. |
| World | months or years | Era change, global calendars, macro events. |

![Time scheduler](assets/diagrams/time_scheduler.png)

## World Time Authority

The World Time Authority owns the absolute tick counter. It should expose only controlled operations.

```yaml
api: WorldTimeAuthority.advance
request:
  partition_id: partition_scene_tavern_brawl_01
  causation_id: turn_000184
  requested_tick_delta: 1
  reason: player_action_resolution
response:
  tick_before: 10488
  tick_after: 10489
  events_due:
    - event_guard_patrol_enters_tavern
  warnings: []
```

The authority should reject direct prose-driven time changes. "Night falls" is a rendering of a committed time advance or scheduled event. It is not itself the clock.

## Event Scheduling

The Event Scheduler holds future events and eligible background actions. Events can be precomputed, deterministic, random under seed, triggered by flags, or controlled by faction logic. The key is that event execution occurs against state before it is narrated.

```yaml
event_sheet:
  event_id: event_raiders_reach_gate
  partition_id: partition_realm_veridian
  scheduled_tick: 16000
  event_type: faction_goal_resolution
  prerequisites:
    - faction: raiders.status == marching
    - location: gate_west.state != destroyed
  effects:
    - set_flag: gate_west_under_attack = true
    - create_event: event_refugees_arrive_market
  missed_event_policy:
    if_players_absent: summarize_on_arrival
    if_players_present: render_scene_immediately
```

## Location Sheets and Route Edges

Location records own exits and route edges. A route is not a line of prose. It is a state edge with cost and constraints.

```yaml
route_edge:
  route_id: route_shoreline_ridge_to_footbridge
  from_location: locus_boothbay_shoreline_ridge
  to_location: locus_boothbay_maiden_tear_footbridge
  base_travel_time_ticks: 24
  traversal_tags: [steep, exposed, wet_stone]
  gates:
    - requires: actor.mobility != impaired
      failure_policy: increase_travel_time_or_require_test
  sensory_transition:
    departing: "salt wind and cave rot"
    arriving: "freshwater noise below the bridge"
```

## Locale-to-World Movement

Locale-to-world movement occurs when play leaves a detailed local scene and enters a broader route, travel summary, realm consequence, or new location. The engine commits a TransitionPacket before it renders the next location.

![Locale transition](assets/diagrams/locale_transition.png)

A TransitionPacket must state origin, destination, route, time cost, carried objects, follower changes, observer changes, events crossed during travel, and conditions applied.

## Causal Cohesion Window

A causal cohesion window is the allowed time separation between related partition events before the engine must summarize, block, or fork. If two troupes operate in the same realm but one is 900 days ahead, the engine cannot casually merge their local facts. It must either isolate branches, summarize one into a later arc, or prevent starting conditions that create contradiction.

The window is based on travel and communication latency. If news can travel between two loci in three days, then realm-level events may become visible within roughly that window. If the loci are months apart by ship, the window is larger. AGE should record the chosen policy rather than leaving it to narrative convenience.

## Dagon-Style Stress Test

The Dagon branch should become a time-location stress test. A player moves through coastal locations while transformation, tide, cult pursuit, freshwater exposure, and final scoring depend on order and timing. The test should assert that the engine preserves these facts:

- each turn has a timestamp or tick;
- each travel segment consumes time;
- the player carries or loses specific objects;
- hidden observers act through scheduled events;
- environmental exposure changes transformation state;
- final scoring is computed from committed state, not from tone.

This is exactly the kind of scenario that proves whether AGE is more than prose.
