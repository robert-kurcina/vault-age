# White Paper 07 — Client, Multiplayer, Communication, and Output

## Plain definition

This subsystem controls how players interact with AGE, how multiple players share state, how communication is scoped, and how verified output is displayed.

## Problem addressed

Multiplayer narrative fails when players see inconsistent state, act out of order, or communicate without scope. AGE needs explicit sync, visibility, and communication rules.

## Responsibility

The client layer owns input modes, choice presentation, free text, ruling requests, sync state, spotlight control, communication channels, voice/display options, replay access, and moderation/audit views.

## Troupe model

The first multiplayer unit is a troupe: a bounded group sharing state, timing, authority policy, and visibility. Troupe isolation protects state coherence and permits table-specific policy.

## Communication

Communication should respect spatial proximity, channel, directive, character voice, visibility, and moderation logging. Original user text should remain available for audit where moderation requires it.

## Reward

Players get natural-language agency without losing shared reality.

## Risk

Poor UI can hide why something happened, interrupt pacing, or expose too much system machinery.

## Mitigation

Separate player-facing prose from optional details: quick explanation, ruling details, replay/audit view, and referee tools.

## Success criteria

Multiple players can act, communicate, receive rulings, and remain synchronized around one coherent troupe state.
