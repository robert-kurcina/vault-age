# Claims and Implementation — Role Service, Actors, and Role Semantic Contracts

## Local definitions

Quality Assurance [QA] means testing and review; Semantic QA tests meaning, authority, role behavior, rules, state, and prose-state agreement.

## Claims

- Roles are contracts, not prompts.
- Role epistemology constrains what a role can know.
- Role behavior must be testable.

## Implementation steps

1. Define Role Semantic Contract schema.
2. Define role knowledge/access rules.
3. Implement output envelopes.
4. Build semantic QA scoring.
5. Add role inheritance/templates.
6. Add audit logs and review tooling.

## Risks and controls

- Risk: role bleed. Control: partition access.
- Risk: prompt-only enforcement. Control: contracts and verifier.
- Risk: high audit cost. Control: automated scoring with human review for exceptions.
