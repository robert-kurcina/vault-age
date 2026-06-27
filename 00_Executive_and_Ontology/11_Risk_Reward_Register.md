# AGE Risk and Reward Register

## Purpose

This register keeps the executive and white-paper layer honest. AGE has meaningful rewards, but it also has high engineering, product, licensing, latency, and governance risk.

| Area | Reward | Risk | Mitigation |
|---|---|---|---|
| Engine-owned state | Persistent consequence and replayability. | High engineering complexity. | Build single-troupe spine first. |
| LLM as Fiction Constructor | Natural prose without state drift from generated text. | Prose may imply invalid facts. | Output Verifier and state-bound context packets. |
| Bridge Layer | Clean boundary between language and state. | Latency and implementation burden. | Typed contracts, quick validation path, narrow module set. |
| Scope ladders | Locale-to-world transitions without simulating everything. | Scale transitions may feel abstract or inconsistent. | Transition packets, TickPolicy tests, state summaries. |
| Lazy ontology | Efficient world generation and author leverage. | Actualized details may conflict with later needs. | Actualization provenance, overlay checks, contradiction tests. |
| Overlays | Economy, law, culture, technology, and faction systems can interact. | Overlay conflicts and hidden complexity. | Overlay proposal contract; no direct mutation. |
| AGEScript | Authored content can remain consequence-first. | Authors may find schemas too technical. | Authoring UX, templates, previews, validation. |
| LMS-Graph | Source-grounded corpus substrate. | Ingestion, licensing, versioning, and source conflict. | Begin with owned/licensed game corpus. |
| CAL | Auditable rules/corpus answers. | Incorrect retrieval may appear persuasive. | Output envelope, alternatives, human decision point. |
| Rules Service | Fast game rulings and arbitration logs. | Slow rulings interrupt play. | Quick ruling and detailed ruling paths. |
| Role Service | Bounded NPCs/advisors/helpers. | Role drift and false authority. | Role Semantic Contracts and Semantic QA. |
| Multiplayer | Shared persistent troupe play. | Concurrency conflicts and player desync. | Troupe isolation, OCC, explicit sync states. |
| Marketplace | Author ecosystem and content leverage. | Content quality and licensing disputes. | Package validation, source declaration, policy gates. |
| Serious play | Training, wargames, exercises, enterprise scenarios. | Overextension before game proof. | Market-selected expansion after MVP evidence. |
| Agent Service | Bounded external action. | Liability, permission, and safety risk. | Defer; require authorization, review, audit, revocation. |
