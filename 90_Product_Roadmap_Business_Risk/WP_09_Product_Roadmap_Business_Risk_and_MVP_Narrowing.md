# White Paper 09 - Product Roadmap, Business Risk, and Minimum Viable Product Narrowing

## Purpose

The Amazing Game Engine [AGE] has broad potential, but its first product must be narrow. A minimum viable product [MVP] is the smallest product that proves the core loop. AGE's core loop is author, play, validate action, resolve through deterministic modules, commit state, render output, verify output, arbitrate rules from sources, replay, test, and improve.

This paper states the product path, rewards, and risks without treating later possibilities as already proven.

## Product Thesis

AGE should enter through role-playing games because games provide the correct pressure environment. A serious role-playing game needs persistent state, rules, exceptions, characters, factions, equipment, locations, time, secrets, table policy, and human adjudication. It is complex enough to test the architecture and low-consequence enough to permit iteration.

The broader opportunity is anchored corpus arbitration. If AGE can answer game-rule questions against a bounded corpus while preserving authority, conflict, and human decision points, the same structure can later be tested against professional corpora. That later path is valuable, but it must not distort the first build.

## MVP Boundary

The first MVP should include the following.

| Component | MVP Treatment |
| --- | --- |
| Core Runtime | Required |
| Bridge Layer | Required |
| State Mutation Engine | Required |
| Event Bus | Required in simple form |
| State Assembler | Required |
| Fiction Constructor | Required, text first |
| Output Verifier | Required in simple form |
| Replay Log | Required |
| Authoring Layer | Required for a small bounded package |
| AGEScript | Required in simple form |
| Partitions | Required in small number |
| TickPolicy | Required for scene and downtime scale |
| Rules Service | Required for one bounded rules corpus |
| LMS-Graph | Required in limited corpus form |
| Role Service | Required for limited NPCs and assistants |
| Semantic QA | Required for core paths |
| Agent Service | Excluded from MVP |
| Professional deployment | Excluded from MVP |
| Marketplace | Excluded from MVP |
| Full multimodal output | Deferred |

The MVP must not become a universal platform on day one. It should prove the action spine and rules arbitration with one or two carefully selected adventures.

## Business Rewards

The game product can offer persistent AI-assisted play that does not collapse into arbitrary prose. It can give authors tools to create stateful worlds and sell structured adventures. It can give Referees a rules clerk, replay assistant, and scenario manager. It can give players natural-language interaction with coherent consequence. It can create a corpus of tested rulings and state transitions that improves the product.

The business also has a possible second line: corpus arbitration tools for professional domains. This should be treated as a later expansion after the system has real evidence from game use.

## Business Risks

The risks are not minor. The product could be too complex to build with available resources. Latency could damage play. Authoring tools could be too demanding for ordinary creators. Existing game engines and AI chat products could absorb parts of the concept. Professional expansion could trigger legal and compliance burdens before product-market fit. Revenue assumptions may be too optimistic. A broad pitch may confuse investors or customers.

The strongest criticism is that "constraint-first" alone is not a moat. Many competitors can claim constraints, retrieval, memory, agents, or tool use. AGE's defensible position must be the integrated system: state authority, partitioned scope, rules arbitration, role contracts, semantic QA, replay, and authoring workflow.

## Cost and Performance Discipline

AGE can become expensive if every action calls multiple models, graph queries, and verifier passes. The MVP should use model calls only where they add value. Deterministic modules should handle deterministic tasks. Fast path actions should use minimal inference. CAL should support quick rulings and detailed rulings separately. Caching should be used where state permits it. Replay and QA should identify expensive paths.

The product should measure latency from the start. A beautiful architecture that makes ordinary play feel slow will fail.

## Development Phases

Phase One builds the runtime spine, simple authoring, one corpus, one troupe, text output, replay, and core QA. Phase Two improves authoring tools, AGEScript, overlays, partitions, roles, and Rules Service. Phase Three adds multiplayer depth, richer client output, marketplace preparation, and certification artifacts. Phase Four may evaluate professional corpus arbitration. Agent Service and external action belong only after role contracts, audit, and human approval are mature.

## Hiring and Team Shape

The early team needs practical engineering more than theoretical architecture. It needs runtime engineering, backend state design, authoring tool design, language-model integration, game systems design, quality assurance, and product leadership. The first hires should be able to build the narrow proof, not merely discuss the platform.

## What Not to Build First

The first product should not build a marketplace, professional compliance platform, autonomous external-action system, universal world generator, full visual engine, or broad role marketplace. These may become valuable later. Building them first would diffuse effort and weaken the proof.

The first product should also avoid supporting too many rules systems. One controlled rules corpus is enough to test the Corpus Arbitration Layer. Multiple corpora can come later after the authority model works.

## Investor and Customer Message

The message should be narrow and concrete. AGE is not "a chatbot for games." It is a state-authoritative narrative engine with source-grounded rules arbitration. The customer should understand that the product protects continuity, supports authors, assists Referees, and enables persistent multiplayer play. The broader corpus arbitration opportunity can be described as future leverage, not as an immediate deliverable.

## Kill Criteria

The roadmap should include kill criteria. If the engine cannot maintain state across sessions, pause expansion. If the Bridge Layer cannot validate ordinary actions, pause expansion. If the Output Verifier cannot prevent factual drift, pause expansion. If authoring tools cannot produce enforceable artifacts, pause expansion. If rules arbitration cannot expose source and conflict, pause expansion. These criteria keep the project honest.

## Success Criteria

AGE's first commercial proof succeeds when a group can play a bounded adventure through natural language, receive coherent stateful output, ask rules questions, obtain source-grounded rulings, replay actions, and continue across sessions without continuity collapse. If that works, the product can widen. If that does not work, the wider business claims should be narrowed or paused.
