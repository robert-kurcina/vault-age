# White Paper 03 - Partitions, State, and Memory

## Document definitions

Amazing Game Engine [AGE] means the complete platform. Partition means a bounded state or knowledge region. Canonical State means the authoritative committed facts of play. Memory means structured, scoped, versioned information rather than a chat transcript. State Assembler means the component that builds bounded context packets. Fiction Constructor means the Large Language Model [LLM] presentation layer. Corpus Arbitration Layer [CAL] means the component that answers corpus questions from sources. Role Service means the subsystem that governs bounded actors.

## Plain definition

Partitions define the boundaries of state and knowledge. Memory is not a transcript. It is structured, scoped, versioned information with ownership, visibility, and propagation rules.

## Problem addressed

Narrative systems fail when all facts are flattened into one context window. AGE separates spatial facts, actor facts, revealed knowledge, hidden knowledge, rules, roles, overlays, and authored content into partitions.

## Responsibility

This subsystem defines Abstract Partitions, Domain Partitions, state ownership, visibility, memory scope, narrative anchors, entity versions, and propagation rules. Abstract Partition means the general partition pattern. Domain Partition means a partition owned by a particular runtime or corpus domain.

## Operating model

A partition determines what can be known, changed, queried, summarized, or propagated. The State Assembler draws from partitions to create context packets. The Fiction Constructor only receives facts appropriate to its output task and visibility constraints.

## Integration

CAL uses corpus partitions. Role Service uses role and memory partitions. Runtime uses spatial and state partitions. These systems may communicate through contracts, but they must not collapse into one undifferentiated memory pool.

## Reward

AGE can preserve hidden information, character-limited knowledge, local consequence, table-specific rules, and versioned corpus state.

## Risk

Poor partition design causes stale facts, overexposure of hidden information, or missed consequences.

## Mitigation

Define partition ownership, visibility, update policy, propagation rules, and version behavior before adding complex content.

## Success criteria

The system can answer: who knows this, where is it true, which version applies, who may change it, and how far does the consequence propagate?
