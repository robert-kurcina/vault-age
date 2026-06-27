# White Paper 02B — Spatial, Narrative, and Temporal Scope

## Plain definition

This subsystem defines how AGE moves from room-scale action to world-scale consequence while keeping time coherent.

## Scope ladders

Spatial: submap, locus, realm, region, world.

Narrative: spotlight, scene, act, chapter, arc, epic.

Temporal: moment, scene time, session time, campaign time, world-history time.

## Problem addressed

A game cannot simulate every person, road, room, economy, and faction every second. It also cannot ignore large-scale consequences. AGE therefore uses scale-appropriate state and TickPolicy.

## Operating model

Local action uses fine resolution. Travel, downtime, faction moves, and world shifts use compressed ticks. A transition packet carries actors between scales and records elapsed time, route, resource use, encounters, background events, knowledge exposure, and arrival conditions.

## Troupe isolation

A troupe is a bounded play group with its own active state, authority policy, timing, visibility, and local overrides. Troupe isolation prevents one group’s unresolved or table-specific state from corrupting another group’s experience.

## Locale-to-world shifts

When local action triggers larger consequences, AGE routes the event upward through partitions. When world events manifest locally, AGE routes pressure downward as visible details, access changes, NPC movement, resource changes, rumors, law, weather, or faction behavior.

## Reward

AGE can show a living world without simulating all world detail at full resolution.

## Risk

Incorrect scale handling can create implausible travel, inconsistent time, or consequences that appear from nowhere.

## Mitigation

Use explicit TickPolicy, transition packets, scope gates, and event visibility rules.

## Success criteria

A character can leave a scene, travel through a larger geography, experience downtime, return to local action, and retain coherent time, resources, state, and world consequences.
