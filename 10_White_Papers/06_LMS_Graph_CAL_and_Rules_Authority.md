# White Paper 6 - LMS-Graph, CAL, and Rules Authority

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE requires a corpus authority system because rules, lore, examples, and prior rulings can conflict. LMS-Graph stores claims and sources. CAL arbitrates among them. The goal is not merely retrieval; it is auditable authority.

## Corpus Claim Model

A source document may contain many claims. A claim is the unit CAL can weigh.

```yaml
corpus_claim:
  claim_id: claim_inventory_object_usability_001
  source_id: source_core_rules_inventory_v01
  authority_tier: canonical_rule
  text: "Physical usability of an object is separate from legal ownership unless a rule or object condition states otherwise."
  concepts:
    - object_usability
    - ownership
    - inventory
  applies_to:
    rulesets: [sarna_len_demo]
    sheet_families: [ObjectSheet]
  conflicts_with: []
  version: 1
```

A source can be canonical, scenario-specific, author note, referee ruling, example, derived summary, or deprecated material. Authority tier matters because the model should not treat all retrieved text as equal.

## CAL Query Flow

![CAL flow](assets/diagrams/cal_flow.png)

CAL should return answer packets.

```yaml
cal_answer_packet:
  query_id: cal_00418
  query_text: "Can this scene use the harbor ambush table?"
  scope:
    partition_id: partition_locus_sunken_harbor_gate
    ruleset: sarna_len_demo
    source_version_set: demo_2026_06_28
  answer:
    decision: allow
    reason: "The table scope is locus_or_scene and the active location has harbor and patrol tags."
  supporting_claims:
    - claim_event_table_scope_002
    - claim_location_tag_matching_004
  conflicts: []
  human_decision_required: false
```

## Authority Tiers

| Tier | Meaning | Example |
| --- | --- | --- |
| Canonical rule | Binding system rule. | Inventory transfer requires object and container versions. |
| Scenario rule | Binding within one adventure or content pack. | This cult reacts to freshwater exposure. |
| Referee ruling | Binding for a campaign after human decision. | This relic cannot be copied. |
| Author note | Useful but not binding. | Designer intended bridge scene to feel dangerous. |
| Example | Demonstrative, not universal. | A sample theft action. |
| Deprecated | Retained for audit but not active. | Earlier branch of a rule. |

## Rules Service Contract

The Rules Service uses CAL but returns a game-resolution contract.

```yaml
api: RulesService.resolve_action
request:
  action_type: stealth_theft
  actor_id: pc_adel
  target_object_id: obj_iron_key
  target_actor_id: npc_bartender_orren
  context_packet_id: ctx_000184
response:
  resolution_basis:
    rule_claims: [claim_stealth_vs_notice_001]
    referee_rulings: []
  required_test:
    test_id: stealth_vs_notice
    actor_stat: stealth
    opposing_stat: notice
  modifiers:
    - source: npc_bartender_orren.distraction
      value: favorable
  deterministic_seed: campaign_7a3f9b:req_000184
```

## Failure Behavior

If CAL finds conflicting active claims at the same authority tier, it should return `human_decision_required: true`. It should not pick whichever source is semantically closer to the prompt. A human ruling can then create a new authoritative claim for the campaign or corpus.

## Acceptance Test

A CAL test should seed three sources: one canonical rule, one example, and one deprecated rule. The question should be answerable only if CAL chooses the canonical rule over the example and excludes the deprecated rule. The answer packet must expose the choice.
