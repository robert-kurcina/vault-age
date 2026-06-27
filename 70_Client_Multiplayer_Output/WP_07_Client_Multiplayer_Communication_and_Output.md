# White Paper 07 - Client, Multiplayer, Communication, and Output

## Document definitions

Amazing Game Engine [AGE] means the complete platform. Client means the player-facing and Referee-facing application surface. Multiplayer means more than one player acting in a shared troupe state. Troupe means a bounded play group with shared state, timing, authority policy, and visibility. User Interface [UI] means the visible controls, screens, prompts, and displays through which users interact with AGE.

## Plain definition

This subsystem controls how players interact with AGE, how multiple players share state, how communication is scoped, and how verified output is displayed.

## Problem addressed

Multiplayer narrative fails when players see inconsistent state, act out of order, or communicate without scope. AGE needs explicit synchronization, visibility, and communication rules.

## Responsibility

The client layer owns input modes, choice presentation, free text, ruling requests, synchronization state, spotlight control, communication channels, voice and display options, replay access, and moderation or audit views.

## Troupe model

The first multiplayer unit is a troupe. Troupe isolation protects state coherence and permits table-specific policy.

## Communication

Communication should respect spatial proximity, channel, directive, character voice, visibility, and moderation logging. Original user text should remain available for audit where moderation requires it.

## Reward

Players get natural-language agency without losing shared reality.

## Risk

Poor UI can hide why something happened, interrupt pacing, or expose too much system machinery.

## Mitigation

Separate player-facing prose from optional details: quick explanation, ruling details, replay or audit view, and Referee tools.

## Success criteria

Multiple players can act, communicate, receive rulings, and remain synchronized around one coherent troupe state.
