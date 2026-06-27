# White Paper 01B — Engine Execution Spine

## Plain definition

The Execution Spine is AGE’s input-to-output pipeline. It is the operational path every player action follows before it becomes narration.

## Spine

```text
User Input
-> Input Coordinator
-> Action Candidate
-> Bridge Layer
-> Domain Module Resolution
-> State Mutation Engine
-> Event Bus
-> State Assembler
-> Fiction Constructor
-> Output Verifier
-> Client Output
-> Replay Log
```

## Problem addressed

Natural-language systems are flexible but ambiguous. Game engines are coherent but rigid. The Execution Spine lets AGE accept flexible input while still enforcing structured state, rules, and timing.

## Operating model

The Input Coordinator extracts intent. The Bridge Layer checks whether the action can be attempted. Domain Modules resolve what happens. State Mutation Engine commits. Event Bus propagates. State Assembler prepares what the Fiction Constructor may know. Fiction Constructor renders. Output Verifier checks. Replay Log records.

## Integration with CAL

If an action depends on rule interpretation, table policy, or corpus evidence, the Bridge Layer can call CAL before module resolution or after conflict detection. CAL returns an ArbitrationEnvelope; the configured human authority may accept or override.

## Rewards

The spine provides auditability, replayability, testability, modularity, and prompt-model independence.

## Risks

The spine can become too slow or too formal for play. Ambiguous inputs may create excessive clarification loops.

## Mitigation

Use three paths: fast action path, quick ruling path, and detailed review path. Do not force detailed arbitration into every in-play action.

## Implementation path

Build the spine with a small module set and instrument every step. The early prototype should prefer visible logs and simple mechanics over hidden complexity.

## Success criteria

A single action can be traced from original user words to final verified output, including validation, resolution, state delta, events, context packet, and replay entry.
