# White Paper 01B - Engine Execution Spine

## Purpose

The Amazing Game Engine [AGE] uses an Execution Spine to turn user language into verified output. The Execution Spine is the ordered input-to-output pipeline followed by a player action, authored event, role action, or rules request. A large language model [LLM] may help interpret language and render prose, but the Execution Spine keeps state, timing, rule application, and replay outside the LLM's authority.

The Execution Spine matters because natural-language play is ambiguous. A player sentence often contains intent, assumption, narration, request, and hoped-for outcome in the same phrase. AGE must separate those parts before it changes the world.

## The Spine

![Figure: AGE Execution Spine](../assets/diagrams/execution_spine.png)

```mermaid
flowchart LR
    A[User words] --> B[Input Coordinator]
    B --> C[Action Candidate]
    C --> D[Bridge validation]
    D --> E[Domain Module resolution]
    E --> F[State Delta]
    F --> G[State commit]
    G --> H[Event Bus]
    H --> I[State Assembler]
    I --> J[Fiction Constructor]
    J --> K[Output Verifier]
    K --> L[Client output and Replay Log]
```

The Input Coordinator converts user words into one or more action candidates. An action candidate is the structured form of a proposed action. The Bridge Layer validates each candidate. A domain module resolves the valid candidate. A domain module is a deterministic resolver with bounded responsibility. The State Mutation Engine commits approved state deltas. A state delta is a proposed canonical change. The Event Bus propagates consequences. The State Assembler builds bounded context. The Fiction Constructor writes the prose. The Output Verifier checks the prose. The Replay Log records the action path.

## Step-by-Step Operation

1. The user supplies words, a client command, or an authored event trigger.
2. The Input Coordinator extracts actor, intent, target, method, hoped-for result, timing, and unresolved assumptions.
3. The Bridge Layer checks identity, authority, scope, visibility, timing, location, inventory, rule availability, active overlays, and entity versions.
4. The Bridge Layer routes the valid candidate to the correct domain module or asks for clarification.
5. The domain module resolves the attempt and proposes one or more state deltas.
6. The State Mutation Engine accepts, rejects, or queues each state delta.
7. The Event Bus emits structured consequences to partitions and schedules.
8. The State Assembler builds a context packet containing only the facts the output layer may use.
9. The Fiction Constructor writes the result.
10. The Output Verifier checks the result against committed state and active constraints.
11. The client receives output and the Replay Log receives the durable record.

This order is important. The player may speak naturally, but the engine must not resolve naturally. It resolves structurally and then renders naturally.

## Clarification, Rejection, and Escalation

Not every input should proceed. If the user says, "I go there," and there are multiple possible destinations, the Bridge Layer should ask a clarification question. If the user says, "I draw the pistol," and the character has no pistol, the Bridge Layer should reject or revise the action. If the user says, "I invoke the obscure edge-case rule from the supplement," the Bridge Layer may call the Corpus Arbitration Layer [CAL]. CAL is the source-grounded service that answers corpus questions from maintained sources. If CAL finds conflicting authority or a table-policy question, the Referee decides.

The Execution Spine should therefore support four paths: immediate resolution, clarification, rejection, and human escalation. A fifth path exists for detailed review when the action involves a complex rules issue, high-impact state change, or source conflict.

## Fast Path and Detailed Path

AGE should not force every action through the slowest path. Walking across a room, checking a backpack, reading a visible sign, or speaking to a present non-player character can use the fast path. A non-player character [NPC] is a character controlled by the system, Referee, or authored scenario rather than by a player. The fast path uses current state, obvious permissions, and a simple resolver.

Detailed path resolution belongs to contested actions, expensive actions, combat, stealth, deception, rules questions, external tool calls, or events that propagate across partitions. A partition is a bounded state or knowledge region. Detailed resolution may require CAL, multiple modules, event scheduling, and explicit replay notes.

## Example

A player writes, "Before the guard notices, I toss the coin under the wagon, slip behind him, and open the side door." This single sentence contains distraction, movement, timing, stealth, and door interaction. The Input Coordinator splits it into candidates. The Bridge Layer checks whether the character has a coin, whether the wagon exists, whether the guard can be distracted, whether there is a side door, and whether the player has enough time. The distraction module resolves the coin. The perception module resolves the guard. The movement module resolves position. The door module resolves access. If any step fails, later steps may be blocked or modified.

The Fiction Constructor should not narrate all steps as successful merely because they make an exciting paragraph. It must render the actual committed sequence.

## Replay as a Design Requirement

Replay is a primary requirement, not a later feature. If AGE cannot replay an action path, it cannot debug rules, certify roles, reproduce sessions, or investigate drift. The Replay Log should store enough information to answer these questions: What did the user say? What did the system think the user meant? What facts were available? Which checks passed? Which module resolved the action? What state delta was proposed? What was committed? What output was rejected or accepted? Which human decision altered the result?

This record allows AGE to improve without relying on vague transcript review. The system can test whether the same input against the same state produces the same result.

## Performance Control

The spine creates latency risk. AGE should use tiered processing. Fast path actions should avoid expensive model calls where possible. Bridge checks can run in parallel when they do not depend on one another. Template prose can handle routine state reports. The Fiction Constructor can stream text only after the necessary committed result exists. Caching can support repeated descriptions, but cached prose must be invalidated when state changes.

Performance tuning should not compromise authority. A fast wrong answer is worse than a slightly slower valid answer in a persistent world.

## Action Candidate Design

The action candidate should be explicit enough for the Bridge Layer to reject it. It should name the actor, intent, target, tool, method, location, expected duration, urgency, resource use, and assumptions. It should also separate the player's desired result from the attempted method. A player may say, "I convince the guard to leave." The desired result is guard departure. The attempted method may be bribery, intimidation, deception, appeal to authority, seduction, or simple persuasion. The system must know which method is being attempted before it can resolve the action.

An action candidate may contain several linked actions. The engine should preserve order when order matters. If the character must unlock a door before moving through it, the movement candidate depends on the lock result. If the character can shout while running, the speech and movement may resolve in parallel or under one time tick.

## Failure Is State

Failure should not be treated as a missing success paragraph. A failed action may spend time, reveal intent, create noise, damage a tool, increase suspicion, trigger a clock, change a relationship, or expose the character. The Execution Spine should record failure with the same seriousness as success. This is how AGE makes consequence persistent.

A failed lockpick attempt that leaves scratches on the lock is different from a clean failure. A failed lie that creates suspicion is different from a lie that simply does not persuade. A failed jump that injures the character is different from a failed jump that leaves the character in place. Domain modules should return meaningful failed-state deltas where the rules or fiction support them.

## Replay as Test Data

Every replay entry is also test data. If users repeatedly correct the same kind of action candidate, the Input Coordinator needs improvement. If the Bridge Layer frequently asks unnecessary clarification questions, its validation policy is too rigid. If the Output Verifier rejects many outputs for the same hallucinated fact type, the Fiction Constructor prompt or context packet needs revision. The Execution Spine therefore doubles as the product's improvement loop.

## Success Criteria

The Execution Spine succeeds when a single action can be traced from original words to verified output. It also succeeds when ambiguous input produces a clear clarification, impossible input produces a clear rejection, source-dependent input produces a CAL arbitration envelope, and high-authority decisions remain with the Referee or designated human authority.
