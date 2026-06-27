# Claims and Implementation — AGEScript, Plot, and Eventing

## Local definitions

Amazing Game Engine [AGE] means the complete platform described by this archive.

## Claims

- AGE uses consequence-first authored structure.
- Event tables are stateful and scoped.
- Rebinding must preserve consequences.

## Implementation steps

1. Define AGEScript scene/precondition/consequence schema.
2. Define event table schema.
3. Implement table weighting and mutation.
4. Implement plot rebinding.
5. Add author preview simulation.
6. Add replay/audit hooks.

## Risks and controls

- Risk: hidden railroading. Control: never erase consequences.
- Risk: combinatorial explosion. Control: rebinding patterns.
- Risk: random-feeling events. Control: preconditions and cooldowns.
