# White Paper 02 - Narrative Scope, AGEScript, and the Living World

## Purpose

The Amazing Game Engine [AGE] is built to support persistent narrative play without forcing the player through fixed branches. Narrative Scope is the story scale at which an event operates. The core levels are spotlight, scene, act, chapter, arc, and epic. AGEScript is the authored scenario and consequence schema layer. The Living World is the background system that advances pressures beyond the immediate scene.

This white paper explains how AGE gives authors structure without turning authored structure into railroading.

## Narrative Scope

Narrative Scope tells AGE how close the story camera is. Spotlight scope concerns one character, choice, exchange, or action. Scene scope concerns the immediate encounter. Act scope concerns a local objective or dramatic unit. Chapter scope concerns a larger mission, journey, dungeon, investigation, or operation. Arc scope concerns a campaign movement. Epic scope concerns world-historical or setting-defining change.

The levels are not literary decoration. They control resolution. A spotlight action may be resolved in seconds. A chapter transition may compress travel, downtime, wounds, supplies, rumor, and faction response. An epic pressure may not appear as a direct scene until it manifests through weather, law, war, migration, trade, technology, or social change.

## AGEScript as Consequence Schema

AGEScript should be read as authored logic, not a screenplay. It defines preconditions, pressures, scenes, triggers, transition rules, costs, state mutations, fail states, success states, and re-entry points. A fixed branch says the players must find the key and then open the vault. AGEScript says the vault exists, the key exists, the lock has properties, guards have schedules, alarms have thresholds, and several consequences can follow depending on what the players do.

This is consequence-first authorship. The author prepares meaningful conditions. The engine preserves what happened. If the players avoid the intended route, the authored pressure does not vanish. It changes form through state-aware continuation.

## The Living World

The Living World is the subsystem that advances background pressures. It does not simulate the entire world every second. It advances relevant partitions through TickPolicy. A TickPolicy is the rule for advancing time within a partition. A partition is a bounded state or knowledge region. The Living World can move factions, advance clocks, spread rumors, change prices, trigger weather, alter travel routes, schedule NPC actions, update legal response, or carry consequences from one scale to another.

The Living World gives AGE continuity beyond the immediate scene. If the players burn a warehouse, the fire may alter city supply, guard deployment, criminal behavior, witness testimony, insurance claims, faction pressure, and future prices. The exact propagation depends on partition scope and event rules.

## Player Derailment

Player derailment is not a bug. It is the ordinary condition of interactive play. The player may kill the expected informant, ignore the quest, destroy the bridge, ally with the villain, sell the artifact, expose the conspiracy early, or flee the region. AGE should not secretly undo those actions to restore the intended plot. It should preserve the consequence and then continue from the new state.

AGEScript handles derailment by binding plot movement to conditions rather than single branches. If the informant dies, the information may be lost, delayed, inherited by another actor, found in notes, discovered through investigation, or become unavailable. The correct continuation depends on what the authored package allows and what the Referee approves. The important rule is that the death remains true. Rebinding can move pressure; it cannot erase cost.

## Scene Rebinding

Scene rebinding is the controlled process of relocating or reshaping dramatic pressure after player action changes the expected path. AGE may relocate a clue, replace a messenger, advance a faction clock, expose a different witness, or move a confrontation to a new site. The system must record why the rebinding happened and what cost was preserved.

Rebinding becomes dishonest if it makes every choice produce the same result. The Referee and authoring tools should treat rebinding as continuity repair, not outcome laundering. A failed negotiation may still start a war. A dead guide may still leave the party lost. A destroyed artifact may still remove the easiest route. AGE can keep the story playable without making all roads identical.

## Basic Adventure Model

The basic adventure is the smallest useful AGEScript package. It should define the location, active actors, initial situation, player objective, optional objectives, obstacles, pressure clocks, available scenes, major transitions, resolution conditions, and aftermath. It should also state what happens if the players refuse the objective, leave the location, fail early, or solve the problem in an unexpected way.

This is where AGE differs from a conventional choose-your-own-adventure structure. A choose-your-own-adventure structure presents fixed choices. AGE presents stateful conditions. The player can attempt actions not listed by the author. The engine tests those actions against the world, rules, and scenario constraints.

## Example

A prepared scene expects the characters to interrogate a captured cultist. Instead, the players release the cultist and secretly follow him. In a brittle script, the scene breaks because the interrogation branch was skipped. In AGE, AGEScript records that the cultist was released, frightened, watched, and followed. The Living World advances his route, contacts, panic, and counter-surveillance. The next scene may become a tailing scene, an ambush, a hideout discovery, or a lost opportunity. The original information may appear differently or not at all.

The system protects both agency and structure. The players changed the route. They did not make the author's preparation useless.

## Risks

The first risk is invisible railroading. If every deviation quietly returns to the same content, players will learn that their choices do not matter. The second risk is brittle authorship. If every deviation breaks the package, authors cannot prepare usable material. The third risk is over-simulation. If every background pressure advances in detail, the system becomes slow and unreadable.

The mitigation is explicit consequence. AGEScript should identify which pressures may rebind, which consequences are fixed, which information can move, which information can be lost, and which costs must remain.

## Author Control

Consequence-first authorship does not remove author control. It changes where control is placed. The author controls the situation, actors, resources, pressures, constraints, and consequences. The author does not control every player decision. This is a better fit for role-playing games because the value of play is that players make meaningful decisions inside a prepared world.

The author should identify which parts of an adventure are essential and which are replaceable. A villain's goal may be essential. The exact tavern where the first clue appears may be replaceable. A prophecy may be essential to the genre. The person who delivers it may change. A murder may be unavoidable if the premise depends on it, but the culprit, witness access, and evidence path may remain interactive.

## Living World Pressure Types

Living World pressure should be categorized. Faction pressure comes from groups with goals. Environmental pressure comes from weather, disease, disaster, scarcity, or terrain. Legal pressure comes from law, patrols, courts, warrants, and punishment. Economic pressure comes from prices, labor, trade, debt, wages, and supply. Social pressure comes from rumor, reputation, family, religion, class, ideology, or fear. Supernatural or science-fiction pressure comes from the setting's special rules.

Categorizing pressure helps AGE decide how it manifests. A legal pressure may become a warrant. An economic pressure may become higher prices. A faction pressure may become recruitment or assassination. An environmental pressure may become blocked travel. A social pressure may become public hostility.

## Referee Use

The Referee should see active pressures and clocks. The system should not hide the world machinery so completely that the Referee cannot adjudicate it. A Referee-facing view can show which pressures are active, which events are eligible, which consequences are hard, which are flexible, and which player actions recently changed the situation. The player-facing view should show only what the characters can observe.

## Success Criteria

This subsystem succeeds when a player can solve, fail, avoid, disrupt, or invert a scene and the adventure continues through recorded consequence. It also succeeds when an author can prepare a meaningful adventure without needing to prewrite every possible branch.
