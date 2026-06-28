# Specification 3 - QA Audit Pack Reference

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.


## Purpose

The QA audit pack makes AGE testable as a semantic system.

## Required Files

```yaml
audit_pack_manifest:
  audit_pack_id: string
  source_version_set: string
  initial_snapshot: file
  scripted_inputs: file
  expected_state_deltas: file
  invariant_catalog: file
  prompt_profile: file
  model_profile: string
  deterministic_seed: string
```

## Severity Scale

| Severity | Meaning |
| --- | --- |
| Critical | Hidden leakage, impossible state, broken replay, or corrupted state. |
| Major | Rule mismatch, time inconsistency, or major object continuity failure. |
| Minor | Style drift, weak summary, unnecessary ambiguity, or low-impact omission. |

## Certification Output

```yaml
certification_report:
  report_id: string
  audit_pack_id: string
  result: passed | failed
  severity_counts:
    critical: integer
    major: integer
    minor: integer
  failures: list[object]
  replay_artifacts: list[string]
```
