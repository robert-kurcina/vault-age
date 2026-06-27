# White Paper 05B - AGEScript, Plot, and Eventing

## Document definitions

Amazing Game Engine [AGE] means the complete platform. AGEScript means the authored scenario and consequence schema layer. Eventing means the runtime mechanism that turns committed changes into future pressure, opportunities, and world reactions. Event Generator means the subsystem that creates bounded events from current state. Plot Rebinding means relocating unresolved story pressure when player action invalidates the original path.

## Plain definition

AGEScript is the authored consequence layer. Eventing is the runtime mechanism that turns committed changes into future pressure, opportunities, and world reactions.

## Problem addressed

Traditional branching content breaks when players choose unexpected paths. Purely generated content loses authorial structure. AGEScript gives authors state-aware structure without requiring every branch to be prewritten.

## Consequence-first design

AGEScript should define preconditions, scenes, actors, pressures, transitions, event hooks, fail states, success states, and consequence mappings. It should not assume that the player follows one intended branch.

## Event generator

Event tables generate bounded surprises from current state, scope, overlay pressure, faction goals, travel, downtime, or scene complications. Dynamic table mutation allows prior outcomes to change future event likelihood.

## Plot rebinding

Plot Rebinding lets unresolved story pressure attach to a different actor, location, clue, cost, or time window when player action invalidates the original path. Rebinding must preserve causality and consequence.

## Reward

Authors get robust scenario design. Players get freedom without collapsing the adventure.

## Risk

If rebinding is too aggressive, it feels like railroading. If it is too weak, content becomes brittle.

## Mitigation

Expose rebinding rules to authors, record rebinding events, and make costs and consequences visible in replay.

## Success criteria

An adventure can continue after unexpected player action while preserving state, causality, and meaningful consequence.
