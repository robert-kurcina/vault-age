# White Paper 07 - Client, Multiplayer, Communication, and Output

## Purpose

The Amazing Game Engine [AGE] is designed for multiplayer persistent narrative. A client is the user-facing application that displays output and receives input. Multiplayer state is the shared and private state that allows multiple players to act in the same world without losing timing, visibility, or authority. Output modality means the form in which AGE presents results, such as text, map, image, audio, interface cards, or summary.

This paper explains how AGE keeps output downstream of state in a multiplayer environment.

## Multiplayer Problem

Single-user generated fiction can hide many errors. Multiplayer cannot. One player's action may affect another player's location, resources, enemies, knowledge, or future options. Two players may act at the same time. One player may know a secret. Another may be misled. A Referee may need to pause a conflict. The client must therefore coordinate timing, visibility, and state authority.

AGE should not treat multiplayer as several isolated chats. It should treat multiplayer as shared state with controlled views.

## Visibility

Visibility rules determine what each user, character, role, and output layer may know. A player may know out-of-character information that the character does not know. A character may know a secret that other characters do not know. A Referee may know hidden state. A faction role may know only what the faction has discovered. The Fiction Constructor should receive only the facts allowed by the current output view.

This prevents private information leakage. If one player opens a hidden vault while separated, another player should not receive a summary that reveals the vault unless the information becomes shared.

## Concurrency

Concurrency occurs when multiple actions touch the same state before the system has resolved all of them. AGE should use explicit state versions and conflict checks. If two players try to grab the same object, the first committed result changes the object version. The second action must be rechecked against the new version. If both actions are simultaneous in the fiction, the appropriate domain module resolves the contest.

The client should make conflicts legible. It can show pending actions, pause for Referee decision, request clarification, or explain that the state changed before the action completed.

## Output Modalities

Text is the first output modality, but AGE should be designed for more. Maps, images, audio, timelines, relationship cards, inventory panels, rule cards, replay views, and summaries can all present state. The rule remains the same: output presents committed or authorized information.

For image generation, AGE should store structured visual descriptors. A visual descriptor is a record of appearance, equipment, injuries, environment, lighting, style constraints, and continuity anchors. The image generator may render from the descriptor. It should not decide that a character has different gear, body, species, wounds, or location unless state changed.

## Summaries and Communication

A summary is a derived output, not a new authority. Session summaries, private notes, character journals, faction reports, and recap cards should derive from replay and visible state. If a summary introduces a new fact, the Output Verifier should reject it or route it to author approval.

Communication between players also needs structure. A whispered message, radio call, public speech, magical sending, forum post, or written letter has sender, recipients, medium, delay, interception risk, and record. AGE should not simply broadcast all communication to all clients unless the medium is public.

## Example

Three players are in the same city. One breaks into the archive. One negotiates with a police captain. One waits outside with a getaway vehicle. The archive player sees locked doors, records, alarms, and guards. The negotiator sees the captain's office and conversation. The driver sees street activity and police movement. If the archive alarm triggers, the Event Bus may send consequences to all three views, but the details differ. The archive player hears alarms inside. The negotiator sees the captain receive a call. The driver sees patrol cars move.

Each output is truthful to the same committed event while preserving local visibility.

## Risks

The first risk is desynchronization. Players may see outputs that imply incompatible states. The second risk is leakage. Private information may appear in public output. The third risk is modality drift. Images, maps, or summaries may contradict text state. The fourth risk is client opacity. If players do not understand why an action paused or failed, the system will feel arbitrary.

The mitigation is shared state authority, per-view context packets, output verification, replay, and clear client explanations.

## Client Views

The client should support distinct views. A player view shows what the player and character may know. A Referee view shows hidden state, clocks, pending events, and arbitration details. An author view shows artifact structure and validation. A replay view shows the action path. A rules view shows source-grounded rulings. These views may use the same underlying state, but they should not expose the same information.

View design is part of authority design. If the client shows hidden state in the wrong place, the backend may be correct while the product still fails.

## Communication Records

Communication should be recorded as state when it matters. A spoken statement may be heard by nearby characters. A written letter may persist as an object. A radio message may be intercepted. A magical message may leave a trace if the setting says so. A private player note may not be character knowledge. AGE should record medium, sender, recipient, time, visibility, and persistence.

This turns communication from loose transcript into game state.

## Output Style and Fidelity

Output style can vary by genre, role, or product, but fidelity should not vary. A grim style, comic style, terse style, or ornate style may all describe the same committed outcome. None may change the outcome. The Output Verifier should therefore check factual fidelity before stylistic preference.

## Success Criteria

This subsystem succeeds when several players can act in one persistent world, receive different but compatible outputs, preserve secrets, resolve conflicts, and replay the shared consequence chain.
