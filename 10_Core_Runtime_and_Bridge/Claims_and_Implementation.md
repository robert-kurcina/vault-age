# Claims and Implementation — Core Runtime and Bridge Layer

## Local definitions

Large Language Model [LLM] means a generative language model used for language interpretation or presentation.

Minimum Viable Product [MVP] means the smallest product that proves the core AGE loop.

## Claims

- The LLM is not a state authority.
- Every canonical mutation passes through validation and commit.
- Replay depends on structured outcomes, not prose memory.

## Implementation steps

1. Define runtime schemas.
2. Build single-troupe execution loop.
3. Implement Bridge validation.
4. Implement State Mutation Engine.
5. Add Event Bus and State Assembler.
6. Add Output Verifier.
7. Add replay and OCC.

## Risks and controls

- Risk: bypassing the Bridge Layer. Control: enforce one write path.
- Risk: latency. Control: narrow MVP modules.
- Risk: scope creep. Control: prove one bounded adventure first.
