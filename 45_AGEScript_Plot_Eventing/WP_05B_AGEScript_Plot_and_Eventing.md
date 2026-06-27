# White Paper 05B - AGEScript Plot and Eventing

## Purpose

The Amazing Game Engine [AGE] uses AGEScript to describe authored scenario structure and event consequences. An event is a structured occurrence that may be triggered by time, action, state, probability, Referee decision, or authored condition. An event generator is the subsystem that creates or selects events from validated conditions. A consequence map is the AGEScript record that connects an event to state changes, future triggers, and visible output.

This paper focuses on plot and eventing as executable structure rather than prose outline.

## Events as State-Carrying Units

An event is not merely a narrative beat. It should know its trigger, scope, eligible actors, prerequisites, output visibility, state deltas, follow-up events, and cancellation conditions. A bandit ambush event may require a road, travel time, bandit faction presence, adequate risk level, and player visibility. A court summons may require legal authority, known identity, jurisdiction, messenger access, and a pending charge.

Because events carry state, they can be tested. The system can ask whether the event was eligible, why it fired, what it changed, and what future consequences it scheduled.

## Plot Without Fixed Branching

AGEScript should not write a plot as a fixed path of scenes. It should write a situation with pressures. A pressure is an active condition that seeks expression through events. The necromancer wants the relic. The city guard wants order. The storm wants to close the road. The rival wants the witness silenced. The disease wants to spread along trade routes. These pressures manifest when their triggers become valid.

This lets the story continue even when players change the route. If the players avoid the haunted bridge, the bridge event may expire, remain waiting, or manifest as a rumor, alternate crossing, delayed attack, or lost opportunity. The rules for that behavior belong in the event record.

## Event Generator Procedure

An event generator should operate in a defined order.

1. Read the active partition and TickPolicy.
2. Identify eligible pressures.
3. Check event prerequisites.
4. Apply scope and visibility limits.
5. Select or generate candidate events.
6. Validate candidates through the Bridge Layer.
7. Commit accepted events or queue future events.
8. Record the result in replay and partition memory.

This order prevents a generator from inserting events that violate state. It also gives the Referee a record of why an event appeared.

## Consequence-First Schema

A consequence-first AGEScript schema should include preconditions, triggers, actor slots, location requirements, state costs, state awards, fail states, success states, visibility rules, follow-up hooks, cancellation conditions, and rebind rules. It should also state which consequences are hard and which are flexible. A hard consequence cannot be erased by rebinding. A flexible consequence may change form while preserving pressure.

For example, "the players learn the duke's secret" is too vague. A stronger schema says the secret exists in the duke's ledger, the steward's testimony, a coded letter, and the rival's blackmail file. Each source has access conditions, risks, and consequences. If the ledger burns, the other sources remain unless state changes remove them.

## Example

The players are expected to attend a masked ball where an assassin will strike. They instead intercept the costume shipment and never attend. AGEScript checks the assassin's objective, schedule, target, disguise source, alternate access, and deadline. The event may become an ambush at the tailor, a postponed assassination, a different disguise, a desperate attack, or a failed assassination that changes faction posture. The masked ball scene was not mandatory. The assassination pressure remains until resolved, transformed, or expired.

## Risks

The first risk is event spam. If every pressure fires whenever technically possible, play becomes noise. The second risk is invisible manipulation. If events always appear to preserve the author's plan, players will feel controlled. The third risk is weak cancellation. If events cannot expire, consequences never close.

The mitigation is event discipline. Events need weights, cooldowns, expiration rules, visibility gates, and cancellation conditions. The Referee should be able to see pending pressures and suppress, delay, or approve major events.

## Event Weighting

Event weighting controls how likely an eligible event is to appear. Weight should come from state, not only author preference. A hungry city increases theft, unrest, disease, and price events. A faction with resources and motive increases targeted action. A quiet road in good weather reduces travel hazard. Weighting makes events feel like consequences rather than random interruptions.

Weights should also be visible to the Referee. The Referee may not need exact numbers in the player-facing text, but the Referee should understand why an event is likely.

## Event Cancellation

Cancellation is as important as triggering. If the players kill the assassin, the assassin's future events should cancel or transform. If they cure the disease, disease events should diminish. If they expose the conspiracy, secret meetings may become panic, flight, or open violence. Without cancellation, the world ignores player success.

Cancellation should emit consequences. Removing a pressure may create relief, retaliation, opportunity, or vacuum. The absence of danger can itself change the world.

## Event Visibility

Not every event is visible when it occurs. A faction may make a secret alliance. A disease may incubate. A court may issue a sealed order. A monster may move underground. AGE should record hidden events while controlling when and how they become visible. Visibility rules prevent the Fiction Constructor from revealing hidden event machinery too early.

## Success Criteria

AGEScript plot and eventing succeed when authored pressure produces coherent consequences across player improvisation without retconning state or flooding play with arbitrary incidents.
