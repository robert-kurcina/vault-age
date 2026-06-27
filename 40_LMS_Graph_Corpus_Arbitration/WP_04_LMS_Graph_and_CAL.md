# White Paper 04 — LMS-Graph and CAL

## Plain definition

LMS-Graph is AGE’s maintained corpus substrate. CAL, the Corpus Arbitration Layer, is the component that answers unstructured questions against that corpus.

The operation is Anchored Corpus Arbitration: ground the answer in source material, expose authority, show conflicts, and preserve the human decision point.

## Problem addressed

LLMs can produce fluent answers from stale or ungrounded memory. Games, professional domains, and institutions need answers tied to source, version, scope, and authority. CAL shifts the LLM from parametric recall to evidence-guided explanation.

## LMS-Graph

LMS-Graph uses graph structures for relationships, citations, dependencies, exceptions, conflicts, version chains, scope, jurisdiction, and concept adjacency. It uses relational structures for tables, thresholds, dates, requirements, classifications, and repeatable facts.

## CAL responsibility

CAL receives a natural-language question, interprets it, chooses corpus partitions, retrieves source evidence, weighs authority, detects conflict, forms a primary answer, preserves alternative readings, identifies the human decision point, and logs the arbitration.

## Rules Service

Rules Service is the first CAL deployment. It should begin with an owned or licensed game rules corpus. That corpus is bounded, versioned, conflict-rich, and low-risk compared to professional domains.

## Output modes

Quick ruling: optimized for play continuity. It gives a concise answer, confidence, authority tier, and human decision point.

Detailed ruling: optimized for review, authoring, testing, or disputes. It includes sources, alternatives, conflicts, deep-dive paths, and override history.

## Reward

AGE gains a source-grounded ruling layer that can improve play, reduce rules friction, capture referee overrides, and create reusable tests.

## Risk

Retrieved evidence can be incomplete, misweighted, out of scope, or too slow for play. A sourced answer can still be wrong if the corpus or authority policy is wrong.

## Mitigation

Use output envelopes, authority tiers, conflict flags, source versioning, scope labels, quick/detailed modes, referee override capture, and corpus-improvement loops.

## Success criteria

A rules question is answered from source-bound evidence rather than model memory, with version, authority tier, confidence, conflicts, and human decision point visible.
