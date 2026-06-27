# AGE Executive Brief

## One-sentence definition

The Amazing Game Engine [AGE] is a state-authoritative narrative simulation and anchored corpus arbitration platform: deterministic services own truth, while language models render outcomes and explain source-grounded rulings.

## What AGE is

AGE lets players, authors, referees, and later institutional users interact through natural language without allowing language generation to become the source of truth. A user may type a free-form action, ask a rules question, challenge a ruling, or request a summary. AGE converts that input into structured candidates, validates them, resolves them through deterministic modules, commits state, retrieves corpus evidence when needed, and only then asks an LLM to present the result.

The system is designed around a strict inversion of ordinary AI narrative products.

```text
Ordinary AI narrative: LLM invents next text, and the text implies what changed.
AGE narrative: Engine resolves what changed, and the LLM explains the committed result.
```

This is the core reason AGE can pursue persistent consequence. State is not memory-like prose. State is a versioned, queryable, auditable system object.

## Why gaming first

A serious role-playing game is the ideal first corpus and runtime environment. It contains rules, exceptions, character state, locations, factions, inventories, time pressure, social context, private information, ambiguous rulings, table authority, house rules, supplements, errata, and version conflicts. These are the same structural problems found in law, regulation, compliance, technical standards, institutional policy, and training scenarios, but a game produces faster feedback with lower consequence.

Gaming is therefore not a toy version of AGE. Gaming is AGE running in its first safe production environment.

## Product layers

AGE has six major product layers.

1. AGE Engine: the runtime spine for state, scope, time, modules, events, context assembly, fiction rendering, output verification, and replay.
2. Authoring Layer: tools for Worldbuilder Authors, System Authors, Role Authors, adventure creators, event tables, AGEScript, overlays, and publication packages.
3. LMS-Graph: the graph/relational corpus substrate built from authoritative or configured source roots.
4. CAL: the Corpus Arbitration Layer that answers unstructured questions against LMS-Graph using source tiers, versioning, conflict flags, and human decision points.
5. Role Service: bounded roles such as NPCs, advisors, tutors, facilitators, authoring helpers, and later professional support roles.
6. Agent Service: a later layer for authorized external action through MCP/API gateways.

RaaS is not used as an umbrella term. It previously blurred roles, rules, retrieval, and arbitration. AGE instead uses precise terms: Role Service, Rules Service, CAL, LMS-Graph, and Agent Service.

## Core runtime architecture

AGE uses a deterministic execution spine:

```text
User Input
-> Input Coordinator
-> Action Candidate
-> Bridge Layer Validation
-> Domain Module Resolution
-> State Mutation Engine
-> Event Bus
-> State Assembler
-> Fiction Constructor
-> Output Verifier
-> Client Output + Replay Log
```

The Bridge Layer is the boundary between language and state. It checks permissions, timing, scope, rules, entity versions, role constraints, active overlays, and partition access. The State Mutation Engine is the only canonical commit path. The Fiction Constructor receives committed truth; it does not create it.

## Scope, time, and world scale

AGE couples three scope ladders.

Spatial scope: submap, locus, realm, region, world.

Narrative scope: spotlight, scene, act, chapter, arc, epic.

Temporal scope: moment, scene time, session time, campaign time, world-history time.

This lets AGE move from a room conversation to a city investigation to a kingdom journey to a world-historical shift without pretending that every scale is simulated the same way. Local events use fine ticks. Travel, downtime, faction activity, and civilizational change use compressed TickPolicies. Locale-to-world transitions are handled through transition packets that validate route, time, resources, encounters, knowledge exposure, background ticks, and event visibility.

## World generation and overlays

AGE uses lazy ontology. The world begins as structured scaffolding: geography, routes, cultures, polities, settlements, factions, economies, religions, technology levels, and major historical pressures. Fine-grained details become real when observed, authored, queried, required by an event, or changed by state. Once actualized, they become canonical.

Overlays are concern-specific lenses over world state. Economy, law, religion, language, technology level, culture, faction politics, genre constraints, role epistemology, and resource flows may inspect state and propose consequences. They do not directly mutate state. All changes pass through validation and the State Mutation Engine.

## CAL and Rules Service

CAL performs Anchored Corpus Arbitration. A user asks a natural-language question. CAL interprets the query, selects corpus partitions, retrieves sources from LMS-Graph, weighs authority, exposes conflicts, identifies the human decision point, and returns an answer envelope.

A Rules Service is the first deployment of CAL. For AGE, the first Rules Service should operate against an owned or licensed game rules corpus. It can answer quick rulings during play and produce deeper rulings for authoring, testing, dispute review, or corpus improvement.

A useful CAL answer includes the user question, interpreted query, corpus partition, retrieved sources, authority tier, version, scope or jurisdiction, confidence, conflicts, primary answer, alternative readings, human decision point, deep-dive paths, and excluded or unsupported material.

## Human authority

AGE improves retrieval, simulation, consistency, presentation, and auditability. It does not replace final authority.

In gaming, final authority is the configured table contract, referee, GM, author, or platform policy. In serious play, it is the facilitator or institution. In professional extensions, it is the licensed practitioner, reviewer, certifier, supervisor, judge, or institution. AGE must always expose where the system stops and where the human or governance authority decides.

## Rewards

AGE offers five high-value rewards.

First, persistent state-coherent narrative. Characters, items, injuries, resources, time, revealed knowledge, faction consequences, and location changes can persist because the engine owns state.

Second, natural-language agency without prose-driven state drift. Players can act conversationally while the engine still validates and resolves structured outcomes.

Third, author leverage. Authors can define worlds, systems, roles, scripts, tables, overlays, and constraints without writing every branch by hand.

Fourth, source-grounded rules arbitration. CAL and Rules Service can answer from a maintained corpus rather than from model memory.

Fifth, expansion optionality. The same architecture can later support serious play, training, enterprise corpora, licensed entertainment content, and selected professional-domain reference tools.

## Risks

The main risks are execution risks, not conceptual impossibilities.

Engineering complexity is high. AGE is a real engine plus corpus infrastructure, not a prompt wrapper.

Latency can damage play if validation, retrieval, generation, and verification are not separated into quick paths and deep paths.

Authoring UX can become too technical if partition, flag, overlay, and script concepts are exposed without good tooling.

Corpus licensing can constrain Rules Service and later CAL deployments.

Human authority and governance must remain visible as the system becomes more persuasive.

Scope creep is the largest product risk. AGE can expand into many domains, but it should first prove one game-native runtime and one bounded game corpus.

## Mitigation strategy

The first product must stay narrow: single-troupe play, bounded spatial scope, deterministic execution, replay log, AGEScript minimum, lazy ontology minimum, one rules corpus, one CAL output envelope, referee override capture, and Semantic QA.

Professional-domain claims should remain downstream. The first evidence should come from game rules arbitration, state coherence tests, replayability, output verification, authoring workflows, and human override analysis.

## Success criteria

AGE succeeds when prose cannot create or alter canonical truth unless validated state changed first.

AGE succeeds when a player can make natural-language choices while the engine preserves rules, time, place, consequence, and replay.

AGE succeeds when a rules question can be answered from source-bound corpus evidence with visible authority tier, version, conflict, and human decision point.

AGE succeeds when authors can build playable, stateful content without hand-authoring every possible branch.

AGE succeeds as a platform when game-native operation produces the data, discipline, and trust required for serious-play and corpus-arbitration expansion.
