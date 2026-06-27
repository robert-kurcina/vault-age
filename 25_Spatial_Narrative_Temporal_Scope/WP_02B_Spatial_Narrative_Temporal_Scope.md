# White Paper 02B - Spatial, Narrative, and Temporal Scope

## Document definitions

Amazing Game Engine [AGE] means the complete platform. Spatial Scope means the physical scale of play. Narrative Scope means the story scale of play. Temporal Scope means the time scale of play. TickPolicy means the rule for advancing time within a partition. Transition Packet means the record that carries actors and consequences between scales. Troupe means a bounded play group with shared active state, timing, authority policy, visibility, and local overrides.

Non-player character [NPC] means a character controlled by the system, Referee, or authored scenario rather than by a player.

## Plain definition

This subsystem defines how AGE moves from room-scale action to world-scale consequence while keeping time coherent.

## Scope ladders

![Figure: Scope Ladders](../assets/diagrams/scope_ladders.png)

```mermaid
flowchart TB
    subgraph Spatial
      S1[Submap] --> S2[Locus] --> S3[Realm] --> S4[Region] --> S5[World]
    end
    subgraph Narrative
      N1[Spotlight] --> N2[Scene] --> N3[Act] --> N4[Chapter] --> N5[Arc / Epic]
    end
    subgraph Temporal
      T1[Moment] --> T2[Scene Time] --> T3[Session Time] --> T4[Campaign Time] --> T5[World-History Time]
    end
```

Spatial Scope runs through submap, locus, realm, region, and world. Narrative Scope runs through spotlight, scene, act, chapter, arc, and epic. Temporal Scope runs through moment, scene time, session time, campaign time, and world-history time.

## Problem addressed

A game cannot simulate every person, road, room, economy, and faction every second. It also cannot ignore large-scale consequences. AGE therefore uses scale-appropriate state and TickPolicy.

## Operating model

Local action uses fine resolution. Travel, downtime, faction moves, and world shifts use compressed ticks. A Transition Packet records elapsed time, route, resource use, encounters, background events, knowledge exposure, and arrival conditions.

## Troupe isolation

Troupe isolation prevents one group's unresolved or table-specific state from corrupting another group's experience. A troupe may have local rulings, visibility limits, time offsets, and authority policies without rewriting the shared corpus or global product state.

## Locale-to-world shifts

When local action triggers larger consequences, AGE routes the event upward through partitions. When world events manifest locally, AGE routes pressure downward as visible details, access changes, NPC movement, resource changes, rumors, law, weather, or faction behavior.

## Reward

AGE can show a living world without simulating all world detail at full resolution.

## Risk

Incorrect scale handling can create implausible travel, inconsistent time, or consequences that appear from nowhere.

## Mitigation

Use explicit TickPolicy, Transition Packets, scope gates, and event visibility rules.

## Success criteria

A character can leave a scene, travel through a larger geography, experience downtime, return to local action, and retain coherent time, resources, state, and world consequences.
