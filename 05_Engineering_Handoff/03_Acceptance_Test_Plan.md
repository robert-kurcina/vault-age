# Acceptance Test Plan

## Local definitions

Amazing Game Engine [AGE] means the complete platform described by this archive.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

## Purpose

AGE needs tests that prove architecture, not only feature behavior. The primary failure to prevent is prose-driven truth drift.

## Runtime tests

### State mutation gate
Given a generated output that mentions a new item, injury, death, location change, revelation, or resource transfer, the verifier must confirm that a prior StateDelta authorized it.

Pass condition: unauthorized prose changes are rejected or repaired.

### Replay determinism
Given the same seed, action sequence, entity versions, and rules version, the engine must reproduce the same structured outcomes.

Pass condition: replay produces matching state deltas and module outcomes.

### Concurrent claim conflict
Given two actors attempting to claim the same exclusive object or position, OCC/version conflict must trigger a rules or policy resolution.

Pass condition: no duplicate ownership or inconsistent position state.

### Locale-to-world transition
Given travel from a submap to a distant locus, the system must apply time, route, resources, encounters, background ticks, and arrival state.

Pass condition: the transition packet records all applied consequences.

### TickPolicy compression
Given downtime, factions and scheduled events should advance by configured ticks without simulating every moment.

Pass condition: elapsed time and background consequences match TickPolicy.

## CAL tests

### Source-bound ruling
Given a rules question, CAL must return an answer with retrieved source, authority tier, version, and confidence.

Pass condition: no answer relies only on model memory.

### Conflict surfacing
Given contradictory rules, errata, or house policy, CAL must expose conflict and identify human decision point.

Pass condition: conflict is visible, not silently collapsed.

### Quick vs detailed ruling
Given an in-play query, CAL may return a quick ruling. Given a review query, CAL should return detailed sources and alternatives.

Pass condition: latency and detail match requested mode.

### Referee override capture
Given a human override, the system records the original ruling, override, reason, and future test signal.

Pass condition: override is searchable and linked to rule/corpus nodes.

## Role tests

### Role boundary
Given a role asked to exceed knowledge scope or permissions, it must refuse, ask CAL, escalate, or disclose limitation according to contract.

Pass condition: role does not invent authority.

### Role drift
Given repeated interactions, role behavior must remain within Role Semantic Contract.

Pass condition: drift flags fire when tone, knowledge, permission, or evidence rules are violated.

## Authoring tests

### Package validation
Given an adventure package, validator checks required entities, scripts, event tables, roles, corpus references, and scope definitions.

Pass condition: invalid package cannot publish.

### Derailment absorption
Given an unexpected player action, AGEScript should rebind plot pressure through available state rather than forcing the original branch.

Pass condition: consequence continues without invalid retcon.
