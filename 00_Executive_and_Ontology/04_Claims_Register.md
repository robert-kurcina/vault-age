# AGE Claims Register

## Purpose

This file separates what AGE asserts, what must be demonstrated, and what should remain deferred. It prevents executive language from becoming untestable hype while still allowing the architecture to be stated with confidence.

## Core architectural claims

| Claim | Meaning | Proof path |
|---|---|---|
| The LLM does not own state. | The Fiction Constructor renders committed outcomes only. | Output verification tests; state mutation audit; adversarial prompt tests. |
| Engine state is authoritative. | Characters, items, locations, time, knowledge, and consequences are stored as structured state. | Replay log; state diff inspection; deterministic reproduction. |
| Prose cannot mutate truth. | Generated text cannot create canonical change unless a state delta already exists. | Output verifier rejection tests. |
| Scope is partitioned. | Spatial, narrative, temporal, corpus, and role domains have bounded scope. | Partition schema; transition packet tests. |
| Time advances by TickPolicy. | Different scopes use different tick rules. | Travel, downtime, scene, faction, and world-history tests. |
| CAL answers from corpus evidence. | Rules and corpus answers are retrieved, tiered, and exposed rather than guessed from model memory. | Source-bound output envelope; blind rules questions; conflict cases. |
| Human authority remains visible. | AGE identifies where a referee, table, author, facilitator, or professional decides. | Human decision point field in CAL and runtime logs. |

## Product claims for the first build

| Claim | Meaning | Proof path |
|---|---|---|
| Natural-language play can be state-coherent. | Players can type ordinary actions while the engine enforces rules and state. | Playtest transcripts matched to replay logs. |
| Game rules arbitration is the first CAL test bed. | A bounded game corpus can validate LMS-Graph/CAL without high professional liability. | Owned/licensed corpus ingestion; referee-graded rulings. |
| Authoring can be assisted without surrendering canon. | Authors can define worlds, roles, overlays, scripts, and tables through structured capture. | Authoring workflow tests; publication package validation. |
| Semantic QA can detect important contradictions. | The system can identify invalid prose, role drift, source conflict, and state mismatch. | Test suite with seeded contradiction cases. |

## Strategic claims

| Claim | Meaning | Guardrail |
|---|---|---|
| AGE can expand beyond gaming. | The architecture generalizes to serious play and selected corpus-guidance domains. | Do not skip the game-native proof path. |
| LMS-Graph can support professional corpora. | The corpus substrate can model source, version, jurisdiction, authority, and conflict. | Licensing, governance, and human authority must be domain-specific. |
| Agent Service can be added later. | Qualified roles may eventually perform external actions through APIs. | Keep out of MVP; require permissions, audit, and review gates. |

## Claims not made

AGE does not claim that LLMs become reliable state managers.

AGE does not claim that authoritative sources are always correct.

AGE does not claim that CAL replaces human judgment.

AGE does not claim that professional-domain deployment should precede game-native validation.

AGE does not claim that all world detail is fully simulated at all times.
