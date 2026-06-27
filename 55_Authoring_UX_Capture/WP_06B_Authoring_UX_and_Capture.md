# White Paper 06B - Authoring Experience and Capture

## Purpose

The Amazing Game Engine [AGE] needs an Authoring Layer that lets creators build worlds, rules packages, roles, adventures, events, overlays, and publication packages without writing every internal schema by hand. The authoring experience is the human-facing workflow for capturing creative intent and converting it into machine-usable constraints.

The Authoring Layer should make structured design possible without forcing authors to think like database engineers.

## Authoring Principle

Authors should speak first in ordinary design language. AGE should then ask precise questions, propose structure, expose missing constraints, and produce editable records. The human author remains the source of creative authority. The system helps convert that authority into enforceable game material.

This is not generic worldbuilding chat. An authoring assistant that merely writes pretty lore does not solve AGE's problem. The output must become usable by the Bridge Layer, State Mutation Engine, Role Service, AGEScript, overlays, and Corpus Arbitration Layer.

## Capture Loop

The authoring capture loop should follow a repeatable process.

1. Intent capture: the author describes the world, scene, rule, role, item, faction, or event.
2. Constraint expansion: AGE identifies implied limits, missing fields, dependencies, and possible conflicts.
3. Structured draft: AGE proposes a machine-readable and human-readable record.
4. Author review: the author approves, edits, rejects, or marks uncertainty.
5. Adversarial testing: AGE tests the record against edge cases and misuse.
6. Publication packaging: accepted records become part of a versioned module.
7. Certification snapshot: tests, approvals, and unresolved issues are recorded.

The loop should be conversational, but its product must be structured.

## Author Types

AGE should distinguish worldbuilder authors from system authors. A worldbuilder author creates setting, geography, culture, factions, characters, equipment, mysteries, adventures, and events. A system author creates rules, procedures, statistics, tests, costs, advancement, combat, economies, and mechanical modules. Some creators will do both, but the tool should not blur the tasks.

A worldbuilder may say that a city has harsh winter rationing. A system author or rules package must define what rationing does to prices, travel, morale, disease, crime, and availability if those effects matter in play. The Authoring Layer should help connect descriptive truth to operational consequence.

## Structured Artifacts

The Authoring Layer should produce several artifact types: world facts, partition definitions, overlay records, role contracts, AGEScript scenes, event generators, item definitions, rule references, faction clocks, transition packets, visibility policies, and test cases. Each artifact should have a version, owner, authority level, dependencies, and publication status.

Publication status matters. A draft note should not behave like canon. A tested module should not be silently overwritten by an experimental idea. A table-specific local override should not modify the global product unless the author explicitly promotes it.

## User Interface Requirements

The authoring interface should show the author what AGE inferred. If the author describes a plague city, the interface should ask whether the plague is magical, biological, social, divine, unknown, or deliberately ambiguous. It should ask what symptoms matter, how transmission works if known, what public authorities believe, what is visible to players, what rules apply, and what consequences should be scheduled.

The interface should also show gaps. A faction with goals but no resources cannot act coherently. A technology overlay with devices but no maintenance assumptions will drift. A role with personality but no knowledge boundary will leak information. A scene with a clue but no alternate access path may become brittle.

## Example

An author writes, "The Stone Maze is an ancient test that rearranges itself when the party lies." AGE should capture this as more than flavor. It should ask what counts as a lie, who judges it, whether omission counts, how the maze changes, what state records the change, whether characters can detect the rearrangement, what happens to separated characters, what event triggers reset, and what the maze wants if it has agency. The resulting AGEScript and partition records make the idea playable.

## Risks

The risk is friction. If authoring requires too many fields too early, creators will abandon the tool. The opposite risk is vagueness. If the tool accepts beautiful but unstructured lore, the runtime cannot enforce it. The Authoring Layer must therefore use progressive disclosure. It should ask only the questions needed for the artifact's intended use, then deepen structure when the author promotes the artifact toward publication or simulation.

## Promotion Pipeline

Authoring should use a promotion pipeline. A note begins as private draft. It becomes structured draft when AGE extracts fields. It becomes testable artifact when required fields and dependencies are present. It becomes accepted module when the author approves it. It becomes published content when packaged with version, license, dependencies, and tests.

This pipeline prevents accidental canon. It also gives authors confidence that experimentation will not corrupt the live product.

## Author Feedback

The Authoring Layer should return useful feedback. It should not merely say that an artifact is invalid. It should say which field is missing, which dependency is unresolved, which overlay conflicts, which role leaks knowledge, which event has no cancellation, which rule reference lacks authority, or which transition has no consequence. The author can then make a creative decision instead of guessing at schema failure.

## Example of Structured Capture

If an author writes, "The captain is loyal until the prince insults her family," AGE should identify a loyalty condition, a trigger condition, a relationship boundary, a possible faction shift, a visibility question, and a future event hook. It should ask whether the insult must be public, whether apology can repair the damage, who counts as family, and whether the captain betrays, resigns, retaliates, or merely withdraws support. That is the difference between flavor and playable state.

## Success Criteria

The Authoring Layer succeeds when a creator can begin with natural language, produce enforceable AGE artifacts, understand what the system inferred, test the artifact against likely misuse, and publish without losing creative control.
