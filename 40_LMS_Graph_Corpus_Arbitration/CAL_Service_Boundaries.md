# Corpus Arbitration Layer [CAL] Service Boundaries

## Local definitions

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Quality Assurance [QA] means testing and review; Semantic QA tests meaning, authority, role behavior, rules, state, and prose-state agreement.

## CAL is

A query-and-arbitration layer over LMS-Graph.

A source-bound answer generator.

A conflict and authority surfacing system.

A provider of quick rulings, detailed rulings, and arbitration logs.

A support layer for Bridge validation, authoring, rules disputes, and QA.

## CAL is not

A role.

A character.

An autonomous agent.

A state mutation service.

A replacement for the referee, table, author, or professional authority.

A guarantee that an authoritative corpus is correct.

## Relation to Rules Service

Rules Service is a CAL deployment against a rules corpus.

## Relation to Role Service

Role Service may call CAL when a role needs source-grounded information. CAL does not define role personality, goals, permissions, or memory.

## Relation to Agent Service

Agent Service may require CAL before action when an external decision depends on corpus guidance. CAL still does not act. Agent Service acts only through permissions and action envelopes.
