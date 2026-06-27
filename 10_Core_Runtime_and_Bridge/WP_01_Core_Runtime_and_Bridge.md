# White Paper 01 — Core Runtime and Bridge Layer

## Plain definition

The Core Runtime is the part of AGE that turns user intent into validated state change. The Bridge Layer is the gate that prevents language, client UI, roles, overlays, and modules from mutating canonical truth without permission.

## Problem addressed

AI narrative systems collapse when the text generator owns state. AGE prevents this by making state mutation a formal engine operation. The LLM may describe what happened, but only after the runtime validates and commits what happened.

## Responsibility

The Core Runtime owns input routing, action validation, module orchestration, state mutation, event publication, context assembly, output verification, and replay logging.

The Bridge Layer owns permission checks, entity version checks, scope checks, timing checks, module routing, overlay proposal review, CAL escalation triggers, and human decision triggers.

## Interfaces

Inputs: ActionCandidate, current state, entity versions, active scope, role constraints, rules references, overlay proposals.

Outputs: ValidationResult, module calls, rejected actions, CAL requests, human decision requests, StateDelta proposals.

## Reward

The reward is enforceable consequence. Characters cannot die, move, learn, heal, spend, acquire, reveal, or change because prose says so. They change because state changed.

## Risk

The risk is complexity and latency. Every validation layer can slow play if the runtime is overbuilt before the first loop is playable.

## Mitigation

Build the narrow runtime first: one troupe, one action pipeline, a few deterministic modules, a simple verifier, and replay. Add richer modules only after the gate works.

## Build path

1. Define ActionCandidate.
2. Define ValidationResult.
3. Build Bridge Layer validation.
4. Build minimum Domain Modules.
5. Build State Mutation Engine.
6. Build Event Bus.
7. Build State Assembler.
8. Build Output Verifier.
9. Build Replay Log.

## Success criteria

A generated paragraph cannot introduce a canonical fact unless a prior StateDelta authorized it. A replay can show why a state change occurred, which module resolved it, and which facts were visible to the Fiction Constructor.
