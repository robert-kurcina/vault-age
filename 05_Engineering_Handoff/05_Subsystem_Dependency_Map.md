# Subsystem Dependency Map

## Local definitions

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Quality Assurance [QA] means testing and review; Semantic QA tests meaning, authority, role behavior, rules, state, and prose-state agreement.

User Experience [UX] means the practical user experience of authoring, play, review, and operation.

Application Programming Interface [API] means a software interface used by one system to request services from another.

## Hard dependencies

The Fiction Constructor depends on State Assembler and Output Verifier.

State Assembler depends on committed state, partitions, visibility rules, role contracts, and active scope.

State Mutation Engine depends on Bridge Layer validation and module resolution.

Domain Modules depend on stable entity schemas and deterministic resolver contracts.

Event Bus depends on committed events and partition subscriptions.

CAL depends on LMS-Graph, corpus source schema, authority tiers, and arbitration envelope.

Rules Service depends on CAL and the game rules corpus.

Role Service depends on Role Semantic Contract, memory scope, permissions, and Semantic QA.

Authoring UX depends on runtime schemas, AGEScript schema, role schema, event table schema, overlay schema, and package validation.

Agent Service depends on Role Service, permissions, action envelopes, external API contracts, audit, review, and revocation.

## Build order summary

1. Entity and state schema.
2. Input/action/validation contracts.
3. Minimal runtime modules.
4. Mutation/event/replay.
5. Context assembly and output verification.
6. Scope and timing.
7. AGEScript and lazy ontology.
8. LMS-Graph/CAL/Rules Service.
9. Role Service and Semantic QA.
10. Authoring and client polish.
11. Marketplace/serious play.
12. Agent Service.
