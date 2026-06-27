# Data Model Seed

## Entity classes

- Actor: player character, NPC, role instance, system actor.
- Location: submap, locus, realm, region, world node.
- Item: physical or abstract possession.
- Resource: time, money, health, supplies, social capital, permissions.
- KnowledgeFact: known, unknown, hidden, revealed, false, contested, source-bound.
- Faction: group with goals, resources, relationships, and TickPolicy.
- Event: committed change or scheduled pressure.
- RuleNode: corpus rule, exception, example, ruling, errata, table policy.
- RoleContract: role behavior specification.
- Overlay: concern-specific state lens.
- ScriptNode: AGEScript scene, precondition, transition, or consequence.

## Required metadata

All canonical state records should support:

- Stable ID.
- Version.
- Scope.
- Partition.
- Provenance.
- Created timestamp.
- Last modified timestamp.
- Authority or owner.
- Visibility.
- Replay references.

## Source/corpus metadata

Corpus records should support:

- Source ID.
- Source type.
- Authority tier.
- Version.
- Effective date.
- Supersession chain.
- Scope/jurisdiction.
- License/access status.
- Conflict state.
- Citation edges.
- Structured facts.

## State visibility

Visibility must distinguish:

- Engine-known.
- Player-known.
- Character-known.
- NPC-known.
- Faction-known.
- Public.
- Hidden.
- Misleading or false.
- Disputed.

The Fiction Constructor must receive only the visibility-appropriate packet.
