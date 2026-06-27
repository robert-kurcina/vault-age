# Minimum Viable Product [MVP] Build Charter

## Local definitions

Amazing Game Engine [AGE] means the complete platform described by this archive.

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Minimum Viable Product [MVP] means the smallest product that proves the core AGE loop.

## Mission

Build a single-troupe AGE runtime that proves engine-owned state, natural-language agency, deterministic resolution, scope/time handling, CAL-based game rules arbitration, output verification, replay, and human override capture.

## Minimum playable loop

1. Player submits natural-language input.
2. Input Coordinator creates an Action Candidate.
3. Bridge Layer validates action against current state, rules, permissions, time, and scope.
4. Domain Module resolves outcome.
5. State Mutation Engine commits validated delta.
6. Event Bus publishes consequences.
7. State Assembler builds context packet.
8. Fiction Constructor renders outcome.
9. Output Verifier checks prose against committed state.
10. Client presents result and stores Replay Log entry.

## Minimum CAL loop

1. Player or referee asks a rules question.
2. CAL interprets the query.
3. CAL selects the game rules corpus partition.
4. LMS-Graph retrieves sources.
5. CAL weighs authority and detects conflict.
6. CAL returns quick ruling or detailed ruling envelope.
7. Referee accepts, modifies, or overrides.
8. Override becomes test and corpus-improvement signal.

## Minimum authoring loop

1. Author defines adventure scope.
2. Author defines locations, roles, rules references, event tables, and AGEScript scenes.
3. Validator checks package consistency.
4. Preview simulation runs sample paths.
5. Package publishes to runtime.

## MVP exit criteria

MVP exits when a bounded adventure can be played, replayed, rules-arbitrated, and audited end-to-end.
