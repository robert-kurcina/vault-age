# White Paper 02B - Spatial, Narrative, and Temporal Scope

## Purpose

The Amazing Game Engine [AGE] uses scope to decide how much detail a situation requires. Spatial Scope is the physical scale of play. Narrative Scope is the story scale of play. Temporal Scope is the time scale of play. A Transition Packet is the record that carries actors, time, resources, visibility, and consequences between scales. A troupe is a bounded play group with shared active state, timing, authority policy, visibility, and local overrides.

Without explicit scope, a persistent world becomes incoherent. A room-scale action cannot be resolved like a continent-scale war. A minute of combat cannot be advanced like six months of faction politics. AGE therefore binds space, story, and time together.

## Scope Ladders

![Figure: AGE Scope Ladders](../assets/diagrams/scope_ladders.png)

```mermaid
flowchart TB
    subgraph Spatial Scope
      S1[Submap] --> S2[Locus] --> S3[Realm] --> S4[Region] --> S5[World]
    end
    subgraph Narrative Scope
      N1[Spotlight] --> N2[Scene] --> N3[Act] --> N4[Chapter] --> N5[Arc or Epic]
    end
    subgraph Temporal Scope
      T1[Moment] --> T2[Scene time] --> T3[Session time] --> T4[Campaign time] --> T5[World-history time]
    end
```

Spatial Scope begins at submap scale, where exact position matters. A locus is a room, street corner, vehicle, campsite, or other immediate place. A realm is a site or local area such as a dungeon, village, building, ship, or neighborhood. A region is a broader territory. A world is the full setting instance or planet-scale frame.

Narrative Scope begins at spotlight scale, where one character's immediate action matters. Scene scope contains the encounter. Act scope contains a local objective. Chapter scope contains a mission, journey, investigation, or adventure. Arc and epic scope contain campaign and world-historical pressure.

Temporal Scope begins at moment scale. Scene time handles the immediate encounter. Session time handles the current play period. Campaign time handles downtime, travel, recovery, politics, and development. World-history time handles long changes such as wars, dynasties, migrations, technological transitions, environmental change, and institutional evolution.

## TickPolicy

A TickPolicy is the rule for advancing time inside a partition. It states the tick size, what background actions occur, what clocks advance, what events are checked, what visibility changes, and what must be recorded. TickPolicy prevents vague time jumps. If the party spends two weeks traveling, the system should know what travel consumed, what events were rolled or scheduled, which factions moved, what rumors spread, and what the arrival condition is.

Different partitions may use different TickPolicy values. A fight may use moment ticks. A city investigation may use hour or day ticks. A kingdom war may use week or month ticks. A star-sector economy may use quarter or year ticks. The engine does not pretend that all systems need the same clock.

## Locale-to-World and World-to-Locale Movement

A locale-to-world shift occurs when a local event creates broader consequence. A murdered noble may change regional politics. A stolen ship may affect trade. A destroyed bridge may alter military movement. A public miracle may change religion, law, media, or crowd behavior. AGE routes such consequences upward through partitions.

A world-to-locale shift occurs when a broad pressure appears in local detail. A famine becomes empty shelves, higher prices, sick children, hungry soldiers, desperate thieves, closed inns, and political anger. A war becomes refugees, patrols, checkpoints, conscription, rationing, rumors, propaganda, and missing family members. AGE routes broad pressure downward into concrete scene material.

These shifts are essential because they make the world feel alive without simulating everything at maximum detail.

## Transition Packets

A Transition Packet carries a change across scale. It should record the origin, destination, elapsed time, actors involved, resource changes, route, hazards, encounters, knowledge exposure, scheduled events, unresolved clocks, visibility changes, and arrival conditions. The packet becomes the bridge between detailed play and compressed play.

For travel, the packet may record days spent, food used, injuries, rumors heard, faction sightings, weather, route condition, and arrival time. For downtime, it may record training progress, income, debts, healing, research, correspondence, and background threats. For world-history jumps, it may record years, political changes, technology availability, inheritance, institutional memory, and what survives into the new period.

## Troupe Isolation

Troupe isolation keeps one group's state from corrupting another group's play. A troupe may have local rulings, discovered facts, modified NPC relationships, altered timing, and house policy. Another troupe may play the same published world without inheriting those local changes. Shared global content remains shared only where the product or author explicitly makes it shared.

This matters for multiplayer and for published adventures. A campaign can branch without rewriting the canonical product for all groups. A local ruling can remain local. A table-specific death, alliance, discovery, or disaster does not need to become universal unless the publisher or product design intends that result.

## Example

The players sabotage a dam in a mountain realm. At locus scale, the system resolves the device, guards, escape, injury, and noise. At realm scale, it resolves flooding, road loss, and local casualties. At region scale, it changes trade, law enforcement, political blame, and military movement. At chapter scale, it alters the mission. At arc scale, it may shift faction strategy. The Transition Packets record which consequences propagate and when local characters see them.

The same event can later return downward. Weeks later, a village scene shows ruined bridges, angry refugees, higher grain prices, and a bounty notice. Those details are not arbitrary color. They are world-to-locale manifestation of recorded consequence.

## Risks

The major risk is inconsistent compression. If time jumps ignore resources, players can travel for free. If world events appear locally without recorded cause, the world feels random. If local actions never propagate upward, the world feels fake. If every event propagates everywhere, the system becomes unusable.

The control is explicit scope gating. Each event type should define how far it normally propagates, what conditions expand it, what delays apply, and what visible forms it may take.

## Resolution Density

Resolution density is the amount of detail AGE uses at a given scope. Moment-to-moment combat may need exact action order, position, injury, and resource use. A month of travel may need route, cost, hazards, discoveries, and arrival condition rather than every footstep. A decade of world history may need institutions, population shifts, technology changes, wars, treaties, and inheritance rather than daily weather.

The system should change density deliberately. A scene can zoom in when the players engage a detail. It can zoom out when detail no longer matters. Zooming is not the same as ignoring state. The Transition Packet preserves what matters across the shift.

## Background Resolution

Background resolution is how AGE advances things away from the player spotlight. It should be lighter than foreground resolution but not arbitrary. A faction does not need a full scene for every meeting, but it should have goals, resources, clocks, and constraints. A road does not need every traveler simulated, but it should have traffic, danger, weather, and control. A city does not need every citizen tracked, but it should have law, mood, prices, events, and rumors.

Background resolution lets the world move while the players are elsewhere. It also gives the Referee concrete material when consequences return to the foreground.

## Scope Errors

Common scope errors include resolving a war as if it were a duel, resolving a duel as if it were a war, letting a local event change the world with no propagation path, letting a world event affect a village with no visible mechanism, and compressing travel without cost. AGE should treat these errors as test cases. If a subsystem often creates them, its TickPolicy or Transition Packet is too weak.

## Success Criteria

This subsystem succeeds when AGE can move from a room conversation to a city investigation to a regional journey to a world shift without losing time, cause, visibility, or resource consequence.
