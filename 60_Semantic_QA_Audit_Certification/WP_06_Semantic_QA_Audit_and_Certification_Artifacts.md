# White Paper 06 - Semantic Quality Assurance, Audit, and Certification Artifacts

## Purpose

The Amazing Game Engine [AGE] requires quality assurance [QA] that tests meaning, not only code execution. Semantic QA is the process of testing whether rulings, role outputs, generated prose, state changes, overlays, and corpus answers obey their contracts. An audit artifact is a durable record that shows what was tested, what passed, what failed, and what human decision changed the result.

AGE cannot rely on demonstration quality. It needs repeatable evidence.

## Semantic Drift

Semantic drift occurs when a system output moves away from its governing contract. A role becomes more knowledgeable than allowed. A ruling ignores a source hierarchy. A generated room contradicts a technology overlay. A summary invents a fact. A visual output changes a character's equipment. A corpus answer presents a weak source as if it were controlling authority.

Semantic drift is different from ordinary software failure. The code may run. The answer may read well. The failure is that the meaning no longer obeys the contract.

## Test Categories

AGE should use several semantic QA categories.

| Test Type | Purpose |
| --- | --- |
| Contract conformance | Checks whether an output obeys its role, rule, overlay, or module contract |
| Metamorphic testing | Checks whether safe rewording preserves the same result |
| Adversarial testing | Applies pressure meant to make the role or engine drift |
| Replay testing | Re-runs action paths to confirm reproducibility |
| Visibility testing | Checks whether hidden facts leak into output |
| Corpus arbitration testing | Checks whether answers use correct sources, versions, and authority tiers |
| Output verification testing | Checks whether prose matches committed state |
| Regression testing | Confirms that a fixed failure does not return |

These tests should be written as product assets, not improvised during review.

## Certification Snapshots

A certification snapshot records the artifact version, test suite, test date, inputs, expected results, actual results, failures, overrides, and approval status. Role Semantic Contracts, rules corpora, world overlays, event generators, and output modalities can all receive certification snapshots.

Certification does not mean perfection. It means the artifact has a known tested boundary. A certified role may still fail in new conditions, but the failure can be added to the test suite. This gives AGE a path for continuous improvement.

## Drift Metrics

AGE may use drift metrics, but it should define them operationally. A drift percentage is meaningful only if the test set, scoring method, severity weighting, and artifact scope are known. A role that fails one harmless tone test is not equivalent to a role that leaks hidden medical data or invents a legal ruling. Severity must matter.

The useful metric is not a marketing number. The useful metric is a record of which contract failed, how often, under what pressure, and what control reduced the failure.

## Audit Trail

Every high-impact output should be auditable. The audit trail should show source selection, authority tier, visible facts, state version, role contract, tool calls, verifier findings, human overrides, and final output. This is necessary for debugging, user trust, professional expansion, and product liability control.

In game use, audit can be lighter during fast play but should remain available for contested rulings, major state changes, and Referee review. In professional use, audit becomes heavier because the consequence of error is higher.

## Example

A rules clerk role answers a combat question. Semantic QA tests whether it used the active rules corpus, respected errata, identified optional rules, avoided table-policy overclaiming, and escalated the final ambiguous case to the Referee. The same question is then rephrased several ways. If the answer changes without a state or source change, the test fails. If the role cites a rule that is not active in the troupe, the test fails. If it gives a confident answer where the corpus has conflict, the test fails.

## Risks

Semantic QA can become expensive. It can also create false confidence if tests are too narrow. A weak test suite certifies only the happy path. The mitigation is to include adversarial tests, known edge cases, user rewordings, hidden information traps, and historical failures.

Another risk is treating QA as a separate late stage. AGE should build QA into development. Every module, role, corpus partition, and output pathway should have tests as it is built.

## Benchmark Corpora

AGE needs benchmark corpora. A benchmark corpus is a controlled set of source material, questions, expected rulings, edge cases, and known traps. For game rules, it should include common actions, rare exceptions, optional rules, contradictory examples, and Referee-only decisions. For roles, it should include secret knowledge traps, tone pressure, tool pressure, and authority challenges.

Benchmarks allow improvement to be measured. Without benchmarks, quality claims remain impressions.

## Severity

Semantic failures should have severity. A typo in output is low severity. A minor tone drift may be low or medium severity. A role revealing a hidden enemy is high severity in a game. A professional role inventing a source or giving unauthorized advice is critical. A visual output changing an injury may be medium or high depending on whether the injury matters mechanically.

Severity helps the team prioritize fixes. It also prevents a misleading aggregate score from hiding dangerous failures.

## Audit Use

Audit should serve practical users. The Referee may use audit to settle a rules dispute. An author may use audit to see why an event fired. An engineer may use audit to debug a module. A corpus owner may use audit to fix source coverage. A professional reviewer may use audit to determine whether the answer can be trusted. The same record can serve each user if it is structured.

## Success Criteria

Semantic QA succeeds when AGE can show why an output was accepted, why a failure was rejected, which contract governed the decision, and what test will catch the same failure later.
