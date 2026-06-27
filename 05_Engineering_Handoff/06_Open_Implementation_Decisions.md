# Open Implementation Decisions

## Purpose

These are implementation decisions, not missing concepts. The architecture defines what must exist. Product and engineering must still choose exact mechanisms.

## Runtime

- Which database technology stores canonical state for the first prototype?
- How much state is relational versus document/graph?
- Which deterministic resolver format is used for random/seeded outcomes?
- How strict is the first Output Verifier?
- What is the maximum acceptable latency for an in-play action?

## CAL

- What owned/licensed game rules corpus is used first?
- What source hierarchy is authoritative for that corpus?
- What is the quick-ruling latency target?
- What is the detailed-ruling latency target?
- How are house rules represented: separate tier, override layer, or table policy partition?

## Authoring

- How much authoring is form-based versus natural-language capture?
- What package format is used for adventures?
- Which validation errors block publication versus warn the author?

## Product

- Is the first play mode solo, GM-assisted, or small troupe?
- Does the first release include voice profiles or text only?
- Does the first release expose replay logs to users or only to QA/admin?

## Governance

- Who can override CAL rulings in the first product?
- Are overrides private to a table, reusable as package policy, or eligible for corpus improvement?
- What moderation records are stored, and for how long?
