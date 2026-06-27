# AGEScript Consequence-First Schema

```yaml
@Action: <unique_action_id>
@Type: <standard | wild_card | jailbreak>
@Allowed: <true | false>
@DerailmentTier: <0-5>

@Validation:
  - condition: <logic_check>
    response: <proceed | warn | resist | reject>

@ConsequenceChain:
  - scope: immediate
    trigger: always
    state_mutations: []
    narrative_hooks: []
  - scope: short_term
    trigger: <turns_elapsed | location_change | event_complete>
    state_mutations: []
    narrative_hooks: []
  - scope: long_term
    trigger: <chapter_end | arc_complete | tick_threshold>
    state_mutations: []
    narrative_hooks: []

@PlotRebind:
  current_plot_invalidated: <true | false>
  new_plot_candidate: <plot_id>
  transition_logic: <condition>
  immediate_goal: <new_goal>

@WorldResistance:
  type: <none | diegetic_rejection | reality_glitch | hard_refusal>
  message_seed: <text_anchor>
```

## Rule

Actions are blocked only when technically impossible, policy-forbidden, or non-diegetic beyond WorldResistance handling. Meaningful diegetic actions are resolved through consequence chains.
