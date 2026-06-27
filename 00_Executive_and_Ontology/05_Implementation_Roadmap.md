# AGE Implementation Roadmap

## Roadmap principle

Build the smallest version that proves the architecture’s hard promises: state authority, natural-language input, deterministic resolution, scope transitions, source-grounded rules arbitration, output verification, replay, and human override capture.

## Phase 0 — Architecture freeze for MVP

Deliverables:

- Ontology frozen around AGE, AGE Engine, LMS-Graph, CAL, Rules Service, Role Service, Agent Service.
- MVP non-goals accepted.
- Core entities and partition schema drafted.
- Interface contracts drafted.
- Owned or licensable game rules corpus selected.

Exit gate: a technical lead can describe what is in V1 and what is explicitly deferred.

## Phase 1 — Single-troupe runtime spine

Deliverables:

- Input Coordinator.
- Action Candidate schema.
- Bridge Layer validation.
- Minimal Domain Modules: character, spatial, inventory, rules, event, time.
- State Mutation Engine.
- Event Bus.
- State Assembler.
- Fiction Constructor prompt contract.
- Output Verifier.
- Replay Log.

Exit gate: a player action can be submitted, validated, resolved, committed, narrated, verified, and replayed.

## Phase 2 — Scope and timing

Deliverables:

- Spatial scopes: submap, locus, realm.
- Narrative scopes: spotlight, scene, act.
- Temporal scopes: moment, scene time, session time.
- TickPolicy schema.
- Transition packets.
- Travel and downtime compression.
- Troupe isolation.

Exit gate: characters can move from local scene to larger travel/downtime context and back without losing state coherence.

## Phase 3 — AGEScript, events, lazy ontology, overlays

Deliverables:

- AGEScript minimum schema.
- Event table schema.
- Plot rebinding rules.
- Lazy ontology actualization rules.
- Overlay proposal contract.
- Technology-level overlay seed.
- Faction/living-world tick seed.

Exit gate: an authored adventure can absorb player deviation, actualize new detail, and propagate consequences without hand-authored branching for every possibility.

## Phase 4 — LMS-Graph and CAL for game rules

Deliverables:

- Source ingestion pipeline.
- Source node and authority tier schema.
- Graph/RDBMS hybrid representation.
- CAL query envelope.
- Quick ruling path.
- Detailed ruling path.
- Conflict detection.
- Referee override capture.
- Rules Service API.

Exit gate: the system can answer game rules questions from corpus evidence with source, version, scope, authority tier, confidence, conflict state, and human decision point.

## Phase 5 — Role Service and Semantic QA

Deliverables:

- Role Semantic Contract schema.
- Role epistemology rules.
- NPC and advisor role prototypes.
- Semantic QA test harness.
- Drift, contradiction, invalid state, and invalid ruling tests.
- Certification artifact format.

Exit gate: roles behave within defined boundaries and generated output can be tested against state, corpus, and role constraints.

## Phase 6 — Authoring and client product

Deliverables:

- Authoring capture workflows.
- Adventure package format.
- Rules corpus package linkage.
- Client interface for input, choices, free text, rulings, and replay.
- Multiplayer synchronization for bounded troupe play.

Exit gate: an author can publish a bounded adventure and players can complete it through natural-language agency with persistent state and replayable rulings.

## Phase 7 — Serious play and market-selected expansion

Deliverables:

- Training scenario package format.
- Facilitator authority model.
- Internal policy or technical documentation corpus pilot.
- Enterprise governance configuration.

Exit gate: AGE can operate outside entertainment while preserving human authority, audit, and corpus boundaries.

## Deferred phase — Agent Service

Agent Service belongs after runtime, CAL, Role Service, QA, and governance are stable. It requires API permissions, action envelopes, review gates, revocation, audit, and liability boundaries.
