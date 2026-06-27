# TickPolicy Specification

## Definition

A TickPolicy defines how time advances inside a partition and how consequences become visible.

## Required fields

- TickPolicy ID.
- Partition ID.
- Scope level.
- Tick size.
- Compression rule.
- Trigger condition.
- Background actors included.
- Scheduled events included.
- Resource consumption rules.
- Visibility rules.
- Ripple routing rules.
- Replay record requirements.

## Tick classes

Moment tick: immediate action, combat, reaction, dialogue beat.

Scene tick: local scene progress, movement within local space, short conversations, searches.

Travel tick: route progress, encounters, supplies, fatigue, weather, delays.

Downtime tick: recovery, crafting, training, investigation, faction moves, relationships.

Faction tick: group goals, resource changes, conflict, influence, political movement.

World-history tick: macro technology, culture, economy, war, migration, religion, ecological change.

## Rule

A higher-scale tick may summarize lower-scale events, but it may not contradict actualized canonical state.
