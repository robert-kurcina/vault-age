# AGE Revised Development Archive — Improvement Pass

This archive is the improved development vault for AGE after the guidance pass. It preserves the corrected ontology from the Claude-thread guidance and tightens the material for practical use: executive briefing, subsystem white papers, implementation handoff, risk/reward control, and testable acceptance criteria.

AGE is treated as the total platform. AGE Engine is the state-authoritative runtime. LMS-Graph is the maintained graph/relational corpus substrate. CAL, the Corpus Arbitration Layer, is the central anchored corpus arbitration component. Rules Service is a CAL deployment for rules systems. Role Service is the bounded role-behavior system. Agent Service is the later MCP/API action layer.

The archive is written for three readers:

1. A founder, investor, or senior reviewer who needs to understand what AGE is, why it is not just an AI chat wrapper, what it can become, and what risks remain.
2. A product or technical lead who needs subsystem boundaries, dependencies, implementation order, and acceptance criteria.
3. A later LLM/thread instance that needs stable concepts, exact vocabulary, and enough structure to continue development without relitigating terminology.

## What changed in this improvement pass

- The executive brief was rewritten for clarity, risk/reward honesty, and product focus.
- The subsystem white papers were normalized into a consistent structure: plain definition, responsibility, interfaces, rewards, risks, build path, and success criteria.
- A new `05_Engineering_Handoff/` directory was added to convert concepts into buildable tracks.
- CAL terminology was strengthened: Anchored Corpus Arbitration is the operation; CAL is the component; Rules Service is the first deployment.
- The human authority model is now explicit across engine, CAL, Role Service, serious play, and professional-domain expansion.
- MVP scope was narrowed into a concrete charter: single-troupe AGE Engine plus a bounded owned/licensed game rules corpus.
- Risk language was preserved, but moved into operational registers rather than weakening the white papers.
- Duplicate compatibility-only files were removed where they created confusion.

## Recommended reading order

Start here:

1. `00_Executive_and_Ontology/00_READ_ME_FIRST.md`
2. `00_Executive_and_Ontology/01_AGE_Executive_Brief.md`
3. `00_Executive_and_Ontology/02_AGE_Ontology_Primer.md`
4. `00_Executive_and_Ontology/03_Subsystem_Index.md`
5. `05_Engineering_Handoff/01_MVP_Build_Charter.md`
6. `05_Engineering_Handoff/02_Interface_Contract_Index.md`
7. `05_Engineering_Handoff/03_Acceptance_Test_Plan.md`

Then read the subsystem white papers in numeric order.
