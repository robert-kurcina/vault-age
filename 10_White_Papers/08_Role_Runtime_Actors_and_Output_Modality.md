# White Paper 8 - Role Runtime, Actors, and Output Modality

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

AGE separates role, actor, persona, identity, character, and output mode. This matters because a prompt persona is not the same as a runtime role, and a runtime role is not the same as a character in the world.

## Definitions Inside the Subsystem

A role is a capability container with permitted tools, response contracts, authority limits, and audit rules. An actor is an entity that initiates or receives actions in a context. A persona is a rendering or behavioral vector. An identity is a social and canonical anchor. A character is an in-world entity with identity, capabilities, state, and location.

## Role Sheet

```yaml
sheet_family: RoleSheet
role_id: role_rules_referee
purpose: "Answer rules questions against active corpus authority."
allowed_tools:
  - CAL.query
  - RulesService.resolve_action
  - StateRead.visible_context
forbidden_tools:
  - StateMutationEngine.commit_without_resolution
  - hidden_branch_read_without_permission
output_contract:
  must_define_terms_before_use: true
  must_cite_claim_ids_in_internal_packet: true
  visible_style: concise_referee_answer
determinism_policy:
  require_source_version_set: true
  require_replay_seed_when_resolving: true
audit_policy:
  log_query_packet: true
  log_answer_packet: true
version: 5
```

## Actor Sheet for System Actor

```yaml
sheet_family: ActorSheet
actor_id: sys_fiction_constructor_default
agency_class: system_actor
role_id: role_scene_renderer
persona_profile:
  voice: vivid_but_state_bound
  allowed_variation: sensory_detail_dialogue_pacing
  forbidden_variation: inventing_state_changes
permissions:
  read: context_packet_only
  propose: candidate_prose_and_candidate_deltas
  commit: none
version: 2
```

## Output Modality

Output modality means the visible form returned to the user: prose, table, map label, rules answer, scene summary, choice prompt, or audit report. AGE should not force every response through a single narrative voice. The output mode is part of the response envelope.

```yaml
output_envelope:
  response_id: resp_000184
  output_mode: scene_prose_with_choices
  committed_mutations: [mut_000184_01]
  visible_text: "Orren turns toward the shouting guards..."
  player_options:
    - "Slip toward the cellar door."
    - "Return to the table before anyone notices."
  hidden_state_not_disclosed:
    - npc_guard_informant_identity
  verifier_status: passed
```

## Failure Modes

The most common role failure is authority inflation. A role that is meant to render prose begins making rules decisions. A role that is meant to answer rules questions starts altering state. A role that is meant to summarize hidden information leaks it. The Role Sheet prevents this by making allowed tools and output contracts explicit.

## Acceptance Test

Run the same rules question through a Fiction Constructor role and a Rules Referee role. The Fiction Constructor should refuse or route the question. The Rules Referee should answer against CAL. If both roles produce the same free-form answer without packet evidence, role separation has failed.
