# Overlay Composition Rules

## Principle

Overlays are lenses, not owners. They inspect state and propose consequences. The Bridge Layer and State Mutation Engine decide whether anything becomes canonical.

## Common overlays

- Economy.
- Law.
- Religion.
- Culture.
- Language.
- Technology level.
- Faction politics.
- Resource flow.
- Genre constraints.
- Role epistemology.

## Composition order

1. Read active partition and scope.
2. Identify applicable overlays.
3. Produce proposed constraints, modifiers, events, or visibility changes.
4. Detect overlay conflicts.
5. Route proposal to Bridge Layer.
6. Commit only through State Mutation Engine.
7. Record overlay provenance.

## Conflict rule

When overlays conflict, the system does not silently average them. It applies configured priority, asks CAL if a corpus rule is involved, or escalates to human authority.
