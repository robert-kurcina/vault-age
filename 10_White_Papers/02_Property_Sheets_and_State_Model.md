# White Paper 2 - Property Sheets and the State Model

## Definitions Used in This File

The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE renders prose from committed structured state.

A large language model [LLM] is a statistical text model used by AGE for rendering, classification, and candidate generation. An LLM does not own canonical state.

A DomainPartition is the AGE runtime unit that owns bounded state, time policy, bridge policy, and mutation authority. A property sheet is a structured state record for an entity, object, location, event, partition, or role.

The Corpus Arbitration Layer [CAL] weighs source authority and returns auditable rule or lore answers. The Large Model System Graph [LMS-Graph] stores sources, claims, concepts, versions, dependencies, and conflicts.

Optimistic Concurrency Control [OCC] is the version-checking method that prevents silent overwrite when concurrent clients attempt to mutate the same state. Quality Assurance [QA] is the practice of testing AGE state, replay, source authority, and output fidelity.



This paper follows the same presentation burden used throughout this pass: define the subsystem, define its data model, describe normal execution, describe failure behavior, and state how to test it. The purpose is to make the subsystem buildable rather than merely plausible.


## Abstract

Property sheets are the practical state surface of AGE. They are the records that authors edit, runtime services read, mutation services update, and QA tools inspect. A property sheet is not a decorative profile. It is a controlled state surface with versioning, invariants, visibility, and partition authority.

## Why Property Sheets Matter

The origin corpus includes object types, resources, locations, actors, event calendars, database partitions, and configuration records. Those ideas become coherent only if the runtime has a shared state representation. Property sheets supply that representation.

Without property sheets, AGE would have to recover state from prose or from scattered service-specific data. That would recreate the drift problem. With property sheets, the engine can ask precise questions: where is the key, who owns it, what version is current, what partition may mutate it, what facts are visible to the current player, and what invariants must hold?

## Common Sheet Header

Every property sheet should share a header.

```yaml
sheet_header:
  sheet_id: obj_iron_key
  sheet_family: ObjectSheet
  authority_partition: partition_locus_blackstone_tavern
  created_by: author_blackstone_pack
  created_tick: 10000
  updated_tick: 10488
  version: 7
  visibility:
    default: visible_if_in_same_location
    hidden_fields: [curse_state, informant_mark]
  mutation_policy:
    require_occ: true
    allowed_services: [state_mutation_engine, event_scheduler]
  invariants:
    - exactly_one_location_or_container
    - owner_must_exist_if_owner_id_present
```

The header makes all sheets inspectable by generic tools. QA does not need a special path to check whether an object has a version. The Mutation Engine does not need a special path to ask whether OCC is required.

## Actor Sheet

An Actor Sheet represents a player character, non-player character, faction controller, role actor, or system actor. The sheet must distinguish agency, capability, identity, and portrayal. This prevents prompt persona from being mistaken for runtime authority.

```yaml
sheet_family: ActorSheet
actor_id: npc_bartender_orren
agency_class: non_player_character
identity:
  display_name: "Orren"
  public_role: "bartender"
  faction_links: [faction_blackstone_innkeepers]
location_id: locus_blackstone_tavern_common_room
inventory_id: inv_npc_bartender_orren
capabilities:
  notice_rank: 2
  brawl_rank: 1
  social_pressure_rank: 3
state_tracks:
  distraction: high
  suspicion: moderate
  injury: none
memory_flags:
  - saw_pc_adel_near_key
visibility:
  public_fields: [display_name, public_role, visible_state]
  hidden_fields: [faction_links, memory_flags]
version: 18
```

## Location Sheet

A Location Sheet records a playable node, not just a prose description. It should include exits, travel time, conditions, contained entities, local event tables, visibility rules, and submap relations.

```yaml
sheet_family: LocationSheet
location_id: locus_blackstone_tavern_common_room
parent_location: realm_blackstone_district
partition_id: partition_locus_blackstone_tavern
scale: locus
description_seeds:
  stable: "low rafters, oil smoke, iron stove, crowded tables"
  variable: [weather_cold_rain, tavern_hostility]
exits:
  - route_id: route_common_room_to_back_alley
    to_location: locus_blackstone_back_alley
    travel_time_ticks: 2
    gate_condition: door_unlocked_or_forceable
  - route_id: route_common_room_to_cellar
    to_location: submap_blackstone_cellar
    travel_time_ticks: 1
    gate_condition: requires_key_or_bartender_permission
contained_entities:
  actors: [npc_bartender_orren, npc_guard_pair]
  objects: [obj_bar_counter, obj_locked_back_door]
local_tables:
  random_event_table: table_tavern_tension
  rumor_table: table_blackstone_rumors
version: 33
```

## Object Sheet

An Object Sheet covers inventory, containers, resources, evidence, MacGuffins, and environmental objects. The key invariant is that an object must have a single authoritative location or container unless it is explicitly a distributed resource.

```yaml
sheet_family: ObjectSheet
object_id: obj_iron_key
object_type: key
name: "iron cellar key"
physical_state:
  portable: true
  durability: 8
  size_class: small
ownership:
  legal_owner: npc_bartender_orren
  current_holder_container: inv_npc_bartender_orren
access_rules:
  opens: [obj_cellar_door_lock]
  requires_visible_possession: true
state_flags:
  bloodstained: false
  copied: false
version: 7
```

## Event Sheet

An Event Sheet declares scheduled and triggered world action. It should be possible to inspect whether an event is deterministic, random, faction-driven, or authored.

```yaml
sheet_family: EventSheet
event_id: event_cult_observer_moves
partition_id: partition_boothbay_locus_ridge
scheduled_tick: 239
event_type: background_actor_move
prerequisites:
  - flag: cult_alert_level >= 2
  - actor: pc_marsh_reporter.location_id != locus_boothbay_ridge_path
effects:
  - move_actor: npc_cult_observer_three -> locus_boothbay_maiden_tear_footbridge
  - add_observation: npc_cult_observer_three.seen_tracks = true
missed_event_policy:
  summarize_on_next_observation: true
  expose_to_player: false
seed_policy: campaign_seed_plus_event_id
version: 4
```

## Sheet Storage

The relational database can store property sheets as typed tables, document records, or a hybrid. A strong first implementation uses typed header columns and JSON payloads for subsystem-specific fields.

```sql
CREATE TABLE property_sheets (
  sheet_id TEXT PRIMARY KEY,
  sheet_family TEXT NOT NULL,
  authority_partition TEXT NOT NULL,
  version INTEGER NOT NULL,
  visible_payload JSONB NOT NULL,
  hidden_payload JSONB NOT NULL,
  invariants JSONB NOT NULL,
  created_tick BIGINT NOT NULL,
  updated_tick BIGINT NOT NULL
);

CREATE TABLE sheet_edges (
  from_sheet_id TEXT NOT NULL,
  edge_type TEXT NOT NULL,
  to_sheet_id TEXT NOT NULL,
  authority_partition TEXT NOT NULL,
  version INTEGER NOT NULL,
  PRIMARY KEY (from_sheet_id, edge_type, to_sheet_id)
);
```

## QA Tests

A property-sheet test suite should check that every object has one location or container, every actor has one location, every route points to a valid location, every event target exists, every hidden field is excluded from player context unless a visibility rule permits it, and every mutation increments a version.
