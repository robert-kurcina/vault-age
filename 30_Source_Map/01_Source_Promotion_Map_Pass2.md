# Source Promotion Map - Presentation Pass 2

This pass promotes the origin branch into technical reader-facing documents. The origin branch remains in `_resource/origin_branch/Archive.zip`, with an extracted copy at `_resource/origin_branch/extracted/`.

| Promoted concept | Source home in origin branch | Pass 2 destination |
| --- | --- | --- |
| Input Coordinator, Fiction Constructor, Consistency Arbiter, State Mutation Engine, Memory Substrate, State Assembler | `B. VISION/02.VISION AGE Core Concept.md` | White Paper 1 and Executive Summary. |
| Spatial state graph, spatial flags, database-tier sketch | `B. VISION/03.VISION AGE An Evolving Game Idea.md` | White Papers 2, 3, and 9. |
| Dagon scenario trace with time and final scoring | `B. VISION/04.VISION AGE Complex Example - Dagon.md` | White Papers 4, 10, and 11. |
| AGEScript as state-first scene language | `C. ARCHITECTURE/09.ARCHITECTURE AGE AGEScript Idea.md` and `C. ARCHITECTURE/10.ARCHITECTURE AGE Plot Derailment.md` | White Paper 5 and Specification 2. |
| Event Generator tables, prerequisites, deterministic seeding, state filtering | `C. ARCHITECTURE/13.ARCHITECTURE AGE Event Generators.md` | White Paper 5. |
| AbstractPartition and DomainPartition, bridge policies, tick policy | `C. ARCHITECTURE/22.ARCHITECTURE AGE AbstractPartition.md` and `C. ARCHITECTURE/24.ARCHITECTURE AGE Partition and RAG.md` | White Papers 3 and 4. |
| Chronological partitioning, troupe overlap, causal windows | `E. EXTENSION/36.EXTENSION AGE Causal Resolution.md` | White Papers 4 and 7. |
| Actors, roles, personas, identity, RaaS separation | `D. IMPLEMENTATION/30.IMPLEMENTATION AGE Actors.md` and `E. EXTENSION/41.EXTENSION AGE RaaS UX.md` | White Paper 8. |
| QA certification, rapid semantic testing, scope manifests | `C. ARCHITECTURE/23.ARCHITECTURE AGE Rapid QA.md` and `D. IMPLEMENTATION/26.IMPLEMENTATION AGE QA Certification.md` | White Paper 10 and Specification 3. |

The presentation model was sharpened against the comparison papers supplied by the user. Those papers use the same general technical burden: target environment, data model, architecture, API, execution behavior, failure behavior, and evaluation. This pass imports that burden without copying their prose.


## AGE Styleguide Application

This pass uses `00_Meta/00_AGE_STYLE_GUIDE.md` as the controlling AGE presentation guide. The practical changes are visible in the archive structure and PDF exports.

1. The origin source remains under `_resource/origin_branch/`.
2. The comparison papers remain under `_resource/comparison_whitepapers/`.
3. The generated PDFs are stored inside `90_PDF_Exports/`.
4. Major PDFs include a table of contents.
5. Major PDFs use a page break before top-level sections.
6. Executive and white-paper PDFs include an Addendum with glossary and citations.
7. Individual white papers and specifications contain local terminology blocks so acronyms and technical terms are defined before use.
8. The main papers use diagrams, property sheets, packets, calculations, database sketches, algorithms, and acceptance tests where the source material supports them.
