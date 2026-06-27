# Claims and Implementation — Spatial, Narrative, and Temporal Scope

## Claims

- Spatial, narrative, and temporal scale are coupled.
- Travel and downtime require validated transition packets.
- Troupe isolation is the MVP multiplayer safety model.

## Implementation steps

1. Define scope enums.
2. Define TickPolicy.
3. Define transition packet schema.
4. Define route and travel metadata.
5. Define flag propagation metadata.
6. Implement troupe isolation.
7. Add world-ripple policy after MVP.

## Risks and controls

- Risk: confusing scale shifts. Control: make transitions explicit.
- Risk: over-simulation. Control: use scoped ticks and flags.
- Risk: troupe chronology conflict. Control: isolate troupes first.
