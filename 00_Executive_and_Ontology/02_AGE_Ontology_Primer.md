# Amazing Game Engine [AGE] Ontology Primer

## Purpose

This primer fixes the project vocabulary. AGE cannot be developed coherently if the same label refers to roles, rules, retrieval, arbitration, and external action. The governing principle is one subsystem, one name.

## Amazing Game Engine [AGE]

AGE is the total platform: runtime engine, authoring layer, game rules corpus, Large Model System Graph [LMS-Graph], Corpus Arbitration Layer [CAL], Role Service, client experience, Semantic Quality Assurance [Semantic QA], audit artifacts, marketplace pathway, serious-play pathway, and later Agent Service.

## AGE Engine

AGE Engine is the deterministic runtime. It receives user input, validates action candidates, resolves actions through modules, commits state, propagates events, assembles context, invokes the Fiction Constructor, verifies output, and records replay.

## Large Language Model [LLM]

LLM means Large Language Model. AGE may use an LLM to interpret natural language or render readable prose, but the LLM does not own canonical state.

## Fiction Constructor

The Fiction Constructor is the LLM-based presentation layer. It turns committed outcomes and bounded context into readable prose. It does not own state, decide facts, arbitrate rules, advance time, reveal hidden information, or change canonical data.

## Large Model System [LMS]

LMS means Large Model System. It includes model inference, retrieval, graph search, agent coordination, tool access, Model Context Protocol [MCP] integration, workspace use, query decomposition, and bounded synthesis. It is broader than an LLM.

## Large Model System Graph [LMS-Graph]

LMS-Graph is the maintained graph/relational corpus substrate. It stores sources, concepts, rules, citations, dependencies, versions, examples, authority tiers, scope, jurisdiction, conflict states, and structured facts.

For the first AGE product, LMS-Graph should ingest a game rules corpus. Later corpora may include licensed entertainment content, internal policy, technical documentation, training material, compliance material, or professional reference corpora.

## Anchored Corpus Arbitration [ACA]

ACA is the operation of answering a user question by grounding it in a bounded corpus, exposing authority, and preserving human decision points.

## Corpus Arbitration Layer [CAL]

CAL is the component that performs ACA. It receives a natural-language query, interprets it, selects corpus partitions, retrieves source evidence, weighs authority, surfaces conflicts, returns a primary answer and alternatives, identifies the human decision point, and logs the ruling.

## Rules Service

Rules Service is a CAL deployment for rule systems. The first Rules Service target is the AGE game rules corpus. Later Rules Services may support other simulations or policy corpora when licensing and governance allow.

## Role Service

Role Service defines bounded actor behavior. It governs non-player characters [NPCs], advisors, tutors, facilitators, authoring helpers, system helpers, and later professional support roles. It uses Role Semantic Contracts, role epistemology, memory scope, permissions, evidence rules, behavioral limits, and audit logs.

Role Service can query CAL, but Role Service is not CAL.

## Agent Service

Agent Service is the later MCP/Application Programming Interface [API]-connected action layer. It allows qualified roles to perform authorized external actions through action envelopes, permissions, review gates, audit logs, and human oversight. It is not part of the first Minimum Viable Product [MVP].

## Roles-as-a-Service [RaaS]

RaaS is deprecated as an umbrella term. Use Role Service for roles, Rules Service for rules, CAL for corpus arbitration, LMS-Graph for corpus substrate, and Agent Service for external action.

## Bridge Layer

The Bridge Layer is the validation and routing boundary between user intent, LLM interpretation, domain modules, and state mutation. It checks whether an action may proceed before any module resolves it.

## Domain Modules

Domain Modules are deterministic services with bounded responsibility: spatial graph, combat, inventory, communication, NPC goals, plot, event generation, living world, technology level, rules arbitration, and role behavior.

## State Mutation Engine

The State Mutation Engine is the only commit path for canonical state. It writes validated deltas with versioning, provenance, and replay records.

## Event Bus

The Event Bus propagates structured consequences across modules and partitions without direct module entanglement.

## State Assembler

The State Assembler builds bounded context packets for the Fiction Constructor. It includes active facts, narrative anchors, local state, role instructions, rule constraints, relevant history, and output boundaries.

## Output Verifier

The Output Verifier checks generated prose against committed state and active constraints. It prevents prose from creating unauthorized facts, contradictions, invalid rulings, or hidden state changes.

## Partition

A partition is a bounded state or knowledge region. Spatial areas, rules corpora, role behavior, technology level, law, culture, faction politics, economy, religion, and plot can all be partitioned.

## Scope hierarchy

AGE couples three ladders:

- Spatial: submap, locus, realm, region, world.
- Narrative: spotlight, scene, act, chapter, arc, epic.
- Temporal: moment, scene time, session time, campaign time, world-history time.

## TickPolicy

A TickPolicy defines how time advances in a partition: duration, step size, compression, background actions, scheduled events, ripple timing, and visibility.

## Lazy ontology

Lazy ontology means the world starts as structured scaffolding and becomes detailed only when observed, authored, queried, required, or affected. Actualized details become canonical.

## Overlay

An overlay is a concern-specific lens over state. Overlays inspect state and propose consequences. They do not commit state directly.

## AGEScript

AGEScript is the authored scenario and consequence schema layer. It defines scenes, preconditions, branches, event hooks, plot rebinding, derailment handling, transition rules, and state-aware output constraints.

## Human authority

Human authority is preserved. AGE retrieves, resolves, structures, explains, and records. The configured table, author, facilitator, institution, reviewer, licensed professional, or judge decides where human judgment is required.
