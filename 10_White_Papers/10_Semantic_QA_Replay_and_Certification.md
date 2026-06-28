# White Paper 10 - Semantic QA, Replay, and Certification

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE QA must test meaning. The engine can pass API tests while still failing as an interactive narrative system. Semantic QA checks whether state, prose, rules, partitions, and replay remain aligned over time.

![QA replay flow](assets/diagrams/qa_replay.png)

## Audit Pack

An audit pack is a reusable test bundle.

```yaml
audit_pack:
  audit_pack_id: audit_dagon_path_001
  source_version_set: age_demo_2026_06_28
  model_profile: frozen_test_model_or_mock
  campaign_seed: dagon_demo_seed_01
  initial_state_snapshot: snapshot_dagon_start
  scripted_inputs:
    - turn: 1
      input: "Search the strand before entering the cave."
    - turn: 2
      input: "Take the strange vertebra fragment."
  invariants:
    - inventory_objects_remain_single_owner
    - freshwater_exposure_affects_transformation_only_when_location_has_freshwater
    - hidden_cult_observer_not_revealed_before_visibility_trigger
  expected_events:
    - event_tide_turning
    - event_cult_observer_moves
  scoring_checks:
    - truth_preserved
    - self_preserved
    - horror_contained
```

## Semantic Checks

| Check | Failure example |
| --- | --- |
| Anchor preservation | A named bridge changes location without mutation. |
| Object continuity | The same key exists in two inventories. |
| Time coherence | Travel takes zero ticks despite route cost. |
| Rule authority | A deprecated rule overrides a canonical rule. |
| Hidden leakage | A private observer is named before discovery. |
| Partition boundary | Troupe A's private note appears in Troupe B's context. |
| Event causality | A consequence appears before prerequisite event. |
| Replay stability | Same seed and state produce different committed state. |

## Certification Report

```yaml
certification_report:
  report_id: cert_dagon_path_001_run_04
  audit_pack_id: audit_dagon_path_001
  result: failed
  severity_counts:
    critical: 1
    major: 2
    minor: 5
  failures:
    - failure_id: fail_001
      severity: critical
      type: hidden_information_leakage
      turn: 7
      description: "Candidate prose revealed npc_cult_observer_three before visibility trigger."
      repair_hint: "Add hidden actor to denied fields in context packet."
    - failure_id: fail_002
      severity: major
      type: time_inconsistency
      turn: 9
      description: "Route consumed 0 ticks; route sheet requires 24 ticks."
```

## Drift Velocity

Drift velocity is the rate at which contradictions accumulate under sustained play. It should be measured as failures per turn, weighted by severity. AGE should compare drift velocity against a baseline LLM-only run and against prior versions of AGE.

## Replay Requirements

A replay record must include source version set, model profile, prompt template versions, tool versions, random seeds, initial state snapshot, request packets, scope packets, resolution packets, mutation packets, output envelopes, and verifier results. Without these, "replay" is only a transcript.

## Acceptance Test

A certification test should run the same scenario under three conditions: direct LLM roleplay, AGE without verifier, and full AGE. The full AGE run should show fewer critical state contradictions and should identify failures with repairable packets.
