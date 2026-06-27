# White Paper 06 — Semantic QA, Audit, and Certification Artifacts

## Plain definition

Semantic QA tests whether outputs, roles, rulings, and state transitions obey AGE’s contracts. Audit artifacts record what happened and why.

## Problem addressed

A generative system can fail in ways ordinary unit tests miss: contradiction, hidden state leakage, invalid rule statements, role drift, unsupported authority, or prose-state mismatch.

## Responsibility

This subsystem owns test harnesses, replay analysis, contradiction detection, output verification, role drift checks, CAL ruling review, override analysis, and certification-style artifacts.

## Certification posture

AGE should first produce certification artifacts, not claim to be an external certifying authority. Artifacts include replay logs, source-bound ruling envelopes, role contract scores, drift reports, override records, and state-prose verification results.

## Reward

AGE can measure its own reliability and convert failures into tests.

## Risk

QA can become performative if tests are not tied to real failure modes.

## Mitigation

Seed tests from play errors, referee overrides, contradiction cases, corpus conflicts, and role violations.

## Success criteria

A failed output or ruling becomes a reproducible test case, and the system can show whether later builds fixed it.
