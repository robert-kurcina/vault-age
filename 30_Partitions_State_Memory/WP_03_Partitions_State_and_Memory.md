# White Paper 03 - Partitions, State, and Memory

## Purpose

The Amazing Game Engine [AGE] partitions state so that a persistent world can remain coherent, scalable, and private where needed. A partition is a bounded state or knowledge region. A state surface is the set of facts a partition owns. Partition memory is the durable record of facts, schedules, visibility, events, and authority within that boundary.

AGE does not treat memory as a chat transcript. It treats memory as structured world state, source state, role state, schedule state, visibility state, and replay.

## Why Partitions Exist

A persistent simulation cannot keep every fact active at all times. It also cannot store everything in one undifferentiated memory pool. A room, city, faction, journey route, rule corpus, player troupe, and professional source collection do not have the same boundaries or authority. Partitions allow each domain to own the facts that belong to it.

A spatial partition may own location, exits, objects, hazards, and local actors. A faction partition may own goals, resources, schedules, secrets, and relationships. A narrative partition may own scene state, unresolved pressures, and transition conditions. A corpus partition may own sources, versions, concepts, citations, and conflict records. A troupe partition may own local rulings, character knowledge, play history, and table policy.

## Partition Topology

Partition topology is the relationship among partitions. A room belongs to a building. A building belongs to a district. A district belongs to a city. A city belongs to a region. A faction may span several regions. A rule corpus may apply across many troupes. A secret may be visible to one character and hidden from another. A partition may therefore be nested, adjacent, overlapping, or linked by event rules.

AGE should not assume that topology is only geographic. A religious order, criminal network, school, guild, government, spaceship crew, research program, court case, or professional standard can all be partitions. The important question is ownership: which system owns the fact, who may see it, how does time advance for it, and how does it propagate consequence?

## State Surface

A partition's state surface defines what can be read or changed through that partition. The state surface should include identity, type, parent partitions, child partitions, visible entities, hidden entities, owned clocks, scheduled events, public facts, private facts, authority rules, active overlays, and open conflicts. The state surface also needs versioning. If two actors try to change the same object from different branches of play, the Bridge Layer must know which version is current.

Optimistic concurrency control is the practical model. A candidate action includes the version of the entities it touches. If the version changed before commit, the Bridge Layer rechecks or rejects the action. This prevents simultaneous multiplayer actions from silently overwriting one another.

## Memory Is Not Retrieval Alone

Retrieval-augmented generation is useful, but it does not by itself solve persistent state. Retrieval-augmented generation means using a search or retrieval process to provide source material to a language model. It can fetch relevant text, but it does not own state mutation, time, authority, private visibility, or causal propagation.

AGE can use retrieval inside partitions. It should not confuse retrieval with memory. Memory must say what happened, when it happened, who knows it, which partition owns it, which rule made it true, whether it is public, whether it is secret, and what future event it schedules.

## Flag Propagation

A flag is a structured marker that a condition exists. The flag may be local, regional, global, public, private, temporary, permanent, visible, hidden, or pending. A stolen relic flag may exist in one room at first. When the theft is discovered, the flag propagates to the owner faction. When the owner issues a bounty, the flag propagates to city law, market actors, informants, and travel checkpoints. When the players hide the relic in another region, a new partition receives it.

Flag propagation should be rule-based. AGE should know which flags remain local, which propagate upward, which propagate laterally, which require discovery, which are delayed, and which expire.

## Privacy and Visibility

Partitions also protect secrets. A player may know facts the character does not know. A character may know facts another character does not know. The Referee may know facts no player knows. A role may be allowed to speak only from character knowledge. The Fiction Constructor must receive only the facts allowed by the current visibility policy.

This is essential for multiplayer. If one player discovers a secret tunnel, another player should not automatically see it in their output unless the knowledge becomes shared. If an NPC is lying, the output may show the lie as speech without revealing the hidden truth. If a role is playing a merchant, it should not reveal system-known future events unless the role's contract allows prophetic knowledge.

## Example

A city partition owns a public curfew. A district partition owns a local riot. A faction partition owns a plan to exploit the riot. A troupe partition owns the fact that the players secretly armed one side. A character partition owns a hidden injury. When the players cross the district at night, the Bridge Layer reads the city curfew, district riot, faction plan if visible through events, troupe-local history, and character injury. The output should reflect only the facts the characters can observe or infer.

If the players later publish evidence of the faction plan, the secret moves from faction-private state to public city state. That is a state mutation, not a summary note.

## Risks

The first risk is fragmentation. If too many partitions exist, the system becomes hard to reason about. The second risk is leakage. If visibility rules are weak, secrets will appear in generated prose. The third risk is stale memory. If partitions do not update when events propagate, old facts will contradict new facts.

The mitigation is to define partition ownership clearly. Each partition should state what it owns, how time advances, how it receives events, how it emits events, and what visibility rules apply.

## Partition Records

A partition record should be practical. It should include an identifier, type, parent, children, authority owner, time policy, state surface, visibility policy, event inputs, event outputs, active overlays, open clocks, and replay references. It should not become a vague label. If a partition cannot say what it owns, the Bridge Layer cannot protect it.

Partition records also need lifecycle. Some partitions are permanent, such as a world or major faction. Some are temporary, such as a combat scene, a journey, a private conversation, or a dream sequence. Temporary partitions should close cleanly, emit their remaining consequences, and archive their replay references.

## Memory Promotion

Not every generated detail deserves permanent state. AGE should decide when a detail is promoted to canonical memory. A passing description of mud on a road may remain ephemeral unless it affects tracking, travel, evidence, disease, or mood. A named innkeeper who becomes important should be promoted. A random rumor may expire. A clue should be recorded. Promotion rules keep memory useful.

The Referee and authoring tools should be able to promote, demote, merge, or retire facts. This prevents the state store from filling with irrelevant detail while preserving the facts that play will rely upon later.

## Source Memory and World Memory

AGE should distinguish source memory from world memory. Source memory stores what the corpus says. World memory stores what happened in the campaign or product world. A rules source may say how falling damage works. World memory says that a character fell from the tower on the third night and injured a leg. Mixing these two kinds of memory causes confusion. The Corpus Arbitration Layer reads source memory. The runtime reads world memory. Some actions need both.

## Success Criteria

This subsystem succeeds when AGE can answer these questions for any important fact: Where is it owned? Who can see it? When did it become true? What made it true? What can change it? Which future processes does it affect?
