# Corpus Arbitration Layer [CAL] Quick Ruling vs Detailed Ruling

## Local definitions

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Quality Assurance [QA] means testing and review; Semantic QA tests meaning, authority, role behavior, rules, state, and prose-state agreement.

## Quick ruling

Quick ruling mode is for live play. It should be fast, concise, and decision-ready.

Minimum fields:

- Primary answer.
- Rule/source reference.
- Authority tier.
- Confidence.
- Conflict flag.
- Human decision point.

## Detailed ruling

Detailed ruling mode is for review, authoring, disputes, QA, or corpus improvement.

Additional fields:

- Interpreted query.
- Corpus partitions searched.
- Retrieved evidence.
- Version and supersession notes.
- Alternative readings.
- Excluded material.
- Deep-dive paths.
- Override history.
- Test-case recommendation.

## Routing rule

Live play defaults to quick ruling unless the referee requests detail or conflict exceeds threshold. Review workflows default to detailed ruling.
