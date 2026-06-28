# White Paper 12 - MVP Implementation Roadmap and Evaluation

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

The MVP should prove the state-authoritative loop in a bounded game. The product should not begin with unrestricted world generation, public marketplace scale, or professional role services. Those expansions depend on the core runtime.

## Build Order

| Phase | Build | Exit test |
| --- | --- | --- |
| 1 | Property sheet schemas and event log. | Load, validate, mutate, and replay simple state. |
| 2 | DomainPartition and TickPolicy. | Scope local scene and advance time correctly. |
| 3 | Location, object, actor, inventory operations. | Move actor, transfer item, preserve versions. |
| 4 | AGEScript scene compiler. | Compile scene to deterministic artifact. |
| 5 | Input Coordinator and Scope Resolver. | Classify and scope 100 mixed inputs. |
| 6 | Rules Service and CAL over bounded corpus. | Answer rules with authority packets. |
| 7 | Fiction Constructor and Output Verifier. | Render scene prose without state contradiction. |
| 8 | Multiplayer spotlight and OCC conflict. | Resolve simultaneous object claim. |
| 9 | Event Scheduler and missed-event summaries. | Execute off-screen events and summarize on observation. |
| 10 | Semantic QA replay harness. | Certify Dagon-style trace against invariants. |

## Minimum Demo Content

The MVP needs one content pack, not a universe. The pack should include:

- one realm;
- three to five loci;
- ten to twenty locations or submaps;
- twenty to fifty objects;
- five to ten actors;
- three event tables;
- five AGEScript scenes;
- one rules subset;
- one Dagon-style stress path;
- one multiplayer conflict path;
- one semantic QA audit pack.

## Engineering Non-Goals

The first build should not implement a full world generator, a marketplace, arbitrary professional roles, third-party plugin ecosystem, unrestricted multi-modal generation, or large-scale public persistent worlds. Each of those can consume the project before the core loop is proven.

## Evaluation Metrics

| Metric | Target for MVP |
| --- | --- |
| State-prose contradiction rate | Fewer than 1 major contradiction per 100 turns. |
| Replay state stability | Same seed and source versions produce same committed state. |
| Hidden leakage | Zero critical hidden-field leaks in audit scenarios. |
| Conflict handling | All OCC conflicts return structured policies. |
| Event correctness | Scheduled events fire at correct ticks or are explicitly deferred. |
| CAL authority | 95 percent of bounded rules questions return correct authority tier. |
| Authoring friction | A trained author can create a small scene without editing raw database rows. |

## Staffing Implications

AGE needs system engineering before broad content staffing. The first team should cover backend state architecture, database design, LLM orchestration, game rules modeling, authoring UX, and QA harness construction. Creative writing is valuable, but it should not lead the architecture. The architecture must make writing safe to render.

## Risk Register

| Risk | Mitigation |
| --- | --- |
| Scope explosion | Keep MVP bounded to one content pack and one rules subset. |
| Authoring burden | Build forms over property sheets; do not expose raw YAML to ordinary users. |
| LLM drift | Use context packets, verifier, replay, and state-first rendering. |
| False determinism | Record source versions, prompt versions, model profile, seeds, and tool versions. |
| Sterile prose | Constrain facts, not voice. Permit sensory and stylistic variation after state is known. |
| Multiplayer confusion | Use spotlight windows, aggregation, and visible conflict policies. |

## Decision Gate

AGE is ready for broader investment only when the MVP can run the same stateful scenario longer and cleaner than an LLM-only baseline, while producing audit packets that explain every committed state change. If it cannot do that, adding more content or more roles will not solve the core problem.
