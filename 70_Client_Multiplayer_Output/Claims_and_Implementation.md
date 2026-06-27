# Claims and Implementation — Client, Multiplayer, Communication, and Output

## Local definitions

User Interface [UI] means the visible controls, screens, prompts, panels, and displays.

## Claims

- The client should hide engine complexity while exposing state-relevant feedback.
- Communication is scoped and logged.
- Troupe play needs spotlight and sync tools.

## Implementation steps

1. Build single-player client loop.
2. Add spotlight state.
3. Add troupe sync states.
4. Implement communication directives.
5. Add quick/detailed output modes.
6. Add replay summaries.
7. Add moderation/original-text logging.

## Risks and controls

- Risk: UI overload. Control: layered detail.
- Risk: slow pacing. Control: spotlight timers and quick actions.
- Risk: communication ambiguity. Control: original/flavored toggles.
