# White Paper 02 — Narrative Scope, AGEScript, and Living World

## Plain definition

Narrative Scope defines how close the story camera is. AGEScript defines authored scenario structure. The Living World system advances background pressures that are larger than the immediate scene.

## Problem addressed

A persistent narrative must handle immediate choices and large consequences without either railroading the player or simulating an entire world at full detail. AGE solves this by binding narrative scope to state scope and time scope.

## Responsibility

Narrative Scope manages spotlight, scene, act, chapter, arc, and epic. AGEScript defines preconditions, scenes, event hooks, transitions, consequences, and plot rebinding. Living World manages faction and macro pressures through TickPolicy and event thresholds.

## Operating model

A spotlight action can affect a scene. Scene outcomes can alter an act. Act outcomes can change a chapter. Chapter and arc pressure can manifest locally through events, rumors, prices, NPC movement, law enforcement, weather, technology, faction posture, or access changes.

## Reward

AGE can preserve player agency while still allowing authored structure. The story can bend around player action because AGEScript binds consequences to state, not to a fixed linear branch.

## Risk

If the system overuses plot rebinding, players may feel that their choices do not matter. If it underuses rebinding, authored content becomes brittle.

## Mitigation

Plot rebinding must preserve cost, consequence, and causality. It may relocate pressure, swap actors, or change timing, but it must not erase committed outcomes.

## Implementation path

Define narrative scope, AGEScript nodes, preconditions, transition rules, consequence mappings, and living-world event hooks. Test with deliberate derailment cases.

## Success criteria

A player can solve, fail, avoid, or disrupt a scene, and the adventure continues through state-aware consequence rather than invalid retcon.
