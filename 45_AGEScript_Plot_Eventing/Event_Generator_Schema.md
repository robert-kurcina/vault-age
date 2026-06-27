# Event Generator Schema

```yaml
event_table_id: wilderness_veridian_forest
scope_level: scene
spatial_tags: ["biome:forest", "realm:veridian"]
narrative_tags: ["peace_time", "low_tension"]
selection_method: seeded_d66
constraints:
  min_unused_entries: 18
  cooldown_ticks: 1440
inheritance:
  fallback_order:
    - locus_specific
    - realm_specific
    - biome_specific
    - universal_default
entries:
  - id: 11
    type: environmental
    title: Wild Magic Surge
    flags_set: ["magic_instability:high"]
    narrative_seed: sudden_localized_storm
    prerequisites: ["magic_system:active"]
  - id: 22
    type: social
    title: Wounded Knight
    flags_set: ["knight_alliance:potential"]
    narrative_seed: knight_mistakes_party_for_nemesis
    prerequisites: ["knights_exist:true"]
  - id: 66
    type: plot_hook
    title: Party Duplicate
    flags_set: ["doppelganger_threat:active"]
    narrative_seed: exact_duplicate_appears
    prerequisites: ["arc_tier:high"]
```

## Selection Rule

The Event Generator rolls only after prerequisites and active plot compatibility are validated. The Fiction Constructor receives a structured event seed, not permission to invent an encounter.
