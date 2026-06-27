# Execution Schemas Summary

## ActionCandidate

Fields: `action_id`, `troupe_id`, `player_id`, `spotlight_id`, `input_text`, `intent_type`, `action_class`, `active_partitions`, `target_entities`, `referenced_rules`, `referenced_concepts`, `required_modules`, `validation_checks`, `ambiguity_prompt`, `created_at_tick`.

## DomainOutcome

Fields: `module_id`, `input_action_id`, `success_state`, `roll_or_resolution_data`, `state_deltas`, `events_emitted`, `narrative_hooks`, `rules_authority`, `time_cost`, `resource_cost`, `followup_required`.

## StateDelta

Fields: `delta_id`, `entity_id`, `partition_id`, `facet`, `operation`, `old_value_hash`, `new_value`, `validation_status`, `commit_policy`, `causal_parent`, `created_by_module`.

## EventRecord

Fields: `event_id`, `event_class`, `source_partition`, `target_partition`, `payload`, `tick`, `causal_importance`, `temporal_scope`, `origin_troupe`, `redaction_policy`, `delivery_mode`.

## ProseGenerationRequest

Fields: `outcome`, `active_state`, `anchors`, `flags`, `narrative_scope`, `spatial_scope`, `time_context`, `role_constraints`, `tl_context`, `tone`, `required_hooks`, `forbidden_claims`, `output_modality`.

## OutputVerificationResult

Fields: `output_id`, `acc_result`, `slc_result`, `pdc_result`, `erc_result`, `tl_result`, `rule_result`, `severity`, `approved`, `required_correction`.
