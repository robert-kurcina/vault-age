# White Paper 03 — Partitions, State, and Memory

## Plain definition

Partitions define the boundaries of state and knowledge. Memory is not a chat transcript; it is structured, scoped, versioned information.

## Problem addressed

Narrative systems fail when all facts are flattened into one context window. AGE separates spatial facts, actor facts, revealed knowledge, hidden knowledge, rules, roles, overlays, and authored content into partitions.

## Responsibility

This subsystem defines AbstractPartition, DomainPartition, state ownership, visibility, memory scope, narrative anchors, entity versions, and propagation rules.

## Operating model

A partition determines what can be known, changed, queried, summarized, or propagated. The State Assembler draws from partitions to create context packets. The Fiction Constructor only receives facts appropriate to its output task and visibility constraints.

## Integration with CAL and Role Service

CAL uses corpus partitions. Role Service uses role and memory partitions. Runtime uses spatial/state partitions. These systems may communicate through contracts, but they must not collapse into one undifferentiated memory pool.

## Reward

AGE can preserve hidden information, character-limited knowledge, local consequence, table-specific rules, and versioned corpus state.

## Risk

Poor partition design causes stale facts, overexposure of hidden information, or missed consequences.

## Mitigation

Define partition ownership, visibility, update policy, and propagation rules before adding complex content.

## Success criteria

The system can answer: who knows this, where is it true, which version applies, who may change it, and how far does the consequence propagate?
