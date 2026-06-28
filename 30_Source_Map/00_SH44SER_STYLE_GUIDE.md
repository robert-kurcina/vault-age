# SH44SER / DXD Style Guide

**Purpose:** Define the prose, structure, rules-presentation, and cleanup conventions for SH44SER and DXD/Sarna Len documents.
**Audience:** LLM assistants, Codex, human contributors, Referees, GMs, and editors producing or revising corpus material.
**Last Updated:** 2026-06-26
**Canonical Authority:** Primary meta-document for style guidance only.
**Location:** `00_Meta/00_STYLE_GUIDE.md`
**Source Weighting:** Primary style evidence is the SH44SER rules manuscript and the Sarna Len / DXD rules manuscript. The prior `00_STYLE_GUIDE.md` is not style canon and must not control prose voice, rules-presentation structure, or Referee guidance.

---

## Foundational Instruction

This style guide exists to help later work preserve the authorial shape of SH44SER and DXD/Sarna Len. It is not a generic RPG writing guide. It is not a consultant writing guide. It is not a prompt-cleanup recipe elevated into canon.

When revising or generating corpus material, weight the actual rules manuscripts first. The prior style guide may be used only as a reminder to remove prompt residue, stale draft scaffolding, or non-corpus presentation artifacts. It must not be used as a model for how SH44SER prose should sound, how a rule should be ordered, or how a Referee-facing section should speak.

The goal is simple: make the new material read as if it belongs inside the rulebook or reference corpus, with the same practical structure, named terminology, concrete explanation, and local paragraph rhythm already present in the source documents.

## Source Authority

Use this order when resolving questions of voice, order, and presentation.

1. **SH44SER rules manuscript.** Controls SH44SER terminology, Referee language, rules order, lore-reference voice, legal and civic framing, powers, Special Abilities, Formians, WPC material, equipment, crime, patrols, combat, and campaign procedure.
2. **Sarna Len / DXD rules manuscript.** Controls DXD terminology, GM language, Sarna Len fantasy prose, DXD Tests, Session Zero / Session One guidance, magic, Trades, setting tone, and Sarna Len-specific procedure.
3. **User-provided corpus files and source notes.** Control the specific canon and local terms for the document being revised.
4. **This style guide.** Controls editorial behavior only.
5. **The prior `00_STYLE_GUIDE.md`.** Non-canonical cleanup artifact. It may suggest cleanup categories, but it does not control prose, rules structure, Referee guidance, or authorial cadence.

Do not harmonize SH44SER and Sarna Len merely because both are written by the same author. They are related corpora with different rulebook voices.

- SH44SER uses **Referee**, **Player**, **Player Character**, **PC**, **NPC**, **game-session**, **Storytelling Session**, **Planning Session**, **Skirmish Session**, **SAP**, **DM**, **TN**, **Prime Requisite**, **Special Ability**, **Complication**, **Mental Quirk**, and setting-specific institutions.
- Sarna Len / DXD uses **GM**, **Players**, **Player-character**, **PC**, **NPC**, **DXD**, **Tests**, **Zed**, **Mustrum**, **picoswarms**, **Traits**, **Trades**, **Deities**, and Sarna Len-specific terms.

Do not import `GM` into SH44SER unless quoting or adapting DXD material. Do not import `Referee` into Sarna Len unless the work is explicitly converting SH44SER language into DXD.

## Corpus Voice Versus UI Iteration Voice

The author's chat and design-iteration voice is not automatically the corpus voice. During live design discussion, compressed phrases may be useful because the participants already know the surrounding argument. These phrases may sound decisive in a chat window but become artificial when copied into a rulebook, setting file, or Referee guide.

Do not promote UI shorthand into corpus prose merely because the author used it while iterating. Treat the phrase as a signpost to the underlying idea, then rewrite the idea in the manuscript voice. The corpus normally explains the thing, gives the consequence, and tells the Referee or GM how it matters.

This rule is not permission to overwrite user source prose. A source note may be rough, misspelled, or written during live iteration while still containing the author's actual prose chain. When the passage carries narrative sequence, cause, consequence, image, judgment, or emotional cadence, preserve it through close editing rather than replacing it with a summary. UI shorthand should be rewritten. Authorial source prose should be preserved.

Avoid importing phrases such as `that is the important boundary`, `the key move`, `high-filter exception`, `dead chemistry still matters`, `this is the clean version`, or `the final stack` into finished files. These are useful design-room phrases. They are not usually the author's instructional prose.

A finished SH44SER or DXD section should usually replace such shorthand with a concrete explanation.

Bad corpus prose:

```text
Human-legible alien Sophonts are a high-filter exception.

Dead chemistry still matters.

That is the important boundary.
```

Better corpus prose:

```text
Only a small portion of Class II Sophonts are familiar enough for Humans to interpret quickly. Most remain difficult to read, dangerous to approach, or biologically incompatible.

Older bio-organic material may still shape later biospheres because precursor molecules, dust, isotopic residues, and degraded organic compounds can survive after living organisms perish.

The Referee should keep appearance, environmental tolerance, intimate compatibility, fertility, and viable offspring as separate questions. A species may pass one of these gates and fail the next.
```

Use short thesis sentences only when they carry the same weight as the source manuscripts. `Fire burns. Rain falls. Wind blows.` works because it establishes a direct rule of reality. A compressed LLM signpost rarely has that same function.

## What the Old Style Guide Can and Cannot Do

The old style guide was derived from incomplete cleanup material. Treat it as a tool note, not as authorial evidence.

It may be used for:

- identifying prompt residue;
- removing transcript scaffolding;
- catching stale branch language;
- reminding editors to make documents standalone;
- identifying generated consultant abstractions when they are obvious;
- separating live canon from speculative or development notes.

It must not be used for:

- modeling SH44SER prose cadence;
- modeling DXD/Sarna Len prose cadence;
- deciding how Referee guidance should be phrased;
- deciding how a rule procedure should be ordered;
- deciding whether paragraphs should be shortened;
- deciding that reference voice should be cleaner, flatter, or more clinical than the manuscript voice;
- replacing the actual corpus with generic handbook style.

If the old guide conflicts with the manuscripts, the manuscripts win.

## LLM Guidance Files Are Not Corpus Prose

LLM guidance files are processing controls. They are not manuscript sources. A file whose purpose is to guide ChatGPT, Codex, or another repository assistant may be direct, schematic, database-like, or blunt because it is not meant to be published.

Do not copy sentences from LLM guidance files into setting, rules, nation, technology, Referee, or lore documents. If a guidance file identifies a concept that belongs in the corpus, rewrite the concept from scratch in the correct manuscript voice.

A guidance file may identify primary homes, imported terms, duplicate files, known drift patterns, banned phrases, and batch decisions. Those are editing controls, not reader-facing prose. The published document should still teach the reader through definition, cause, consequence, example, institution, and Referee use.

Use filenames that make this role clear when possible, such as `00_DO_NOT_PUBLISH_LLM_GUIDANCE.md`, `00_LLM_GUIDANCE_TEMPLATE.md`, or another explicit local equivalent. If the file is intentionally reader-facing, it should say so in its Purpose line.

## Core SH44SER Voice

SH44SER prose is a rules manual, setting reference, and practical Referee tool at the same time. It is not purely encyclopedic. It does not usually state isolated facts without explaining why they matter. It often moves from a definition to the consequence of that definition, then to how the Referee or player should use it.

The ordinary SH44SER voice is:

- declarative;
- practical;
- concrete;
- interested in record keeping;
- interested in consequences;
- willing to use long explanatory paragraphs when needed;
- willing to use moral language when describing exploitation, corruption, cruelty, oppression, violence, or abuse of power;
- comfortable with real-world analogies, counterfactual history, institutional logic, and mechanical limits;
- willing to tell the Referee what to decide, record, award, restrict, or adjudicate.

SH44SER often explains a subject by saying what it is, what it does, what it costs, who controls it, and what happens when it goes wrong. This should be preserved.

This voice is not the same as a sequence of clipped analytical conclusions. A SH44SER paragraph may be long, slightly idiosyncratic, and full of cause-and-effect movement. It commonly uses phrases such as `As a result`, `However`, `In return`, `Therefore`, `At the very least`, `Usually`, `Often`, and `Maybe` to keep the reader moving through the logic. Do not replace that motion with a series of isolated maxims.

When a technical idea is complex, write the reader path. Name the thing, explain the ordinary case, explain the pressure or danger, and then give the exception. The manuscripts often sound like a Referee explaining why the world behaves a certain way, not like a consultant naming a boundary condition.

## Core DXD / Sarna Len Voice

Sarna Len / DXD shares the author’s preference for concrete explanation and consequence, but its voice is different. It is more openly mythic, more comfortable with dramatic language, and more likely to introduce setting material through named wonders, ruins, peoples, gods, tools, and dangers.

DXD rules prose is still practical. It explains who rolls, what dice are used, what modifiers mean, and how the GM should teach the game. Sarna Len setting prose may begin with strong declarations, strange images, and named cultural or magical phenomena before narrowing into rules.

Sarna Len / DXD may use:

- `GM` rather than `Referee`;
- `Test` rather than SH44SER-specific check language when writing DXD procedure;
- direct teaching sections such as Session Zero, Session One, and Session X;
- in-world quotations when they are deliberately part of the manuscript;
- fantasy and science-fantasy explanation mixed together.

Do not remove the mythic or strange quality from Sarna Len to make it read like SH44SER. Do not add Sarna Len’s mythic dramatic voice to SH44SER reference prose unless the SH44SER section itself is intentionally in-world or dramatic.

Sarna Len often accepts more wonder, menace, and rough-edged grandeur than SH44SER. It may name a thing, place it in old history, explain how common people misunderstand it, then reveal the hidden machinery underneath. Even then, the prose normally keeps moving through concrete people, places, tools, monsters, gods, weather, gates, tunnels, cities, and costs. Do not replace that with abstract labels or polished summaries.

## Local Structure Matters

Preserve local structure whenever it is recognizable and functional. Presentation order may be refined, but the author’s local structure should not be replaced with generic executive-summary structure.

A common SH44SER pattern is:

1. name the topic;
2. state whether it is optional, required, default, or under Referee control;
3. define the thing in plain language;
4. explain why it exists in the setting or in play;
5. provide the rule, calculation, table, or procedure;
6. state exceptions or limits;
7. give one or more examples;
8. tell the Referee or player what to record, award, restrict, or cross-reference.

A common Sarna Len / DXD pattern is:

1. name the topic;
2. give a direct explanation or setting image;
3. define the relevant game term;
4. explain how the GM or Players use it;
5. provide a small list, example, or table;
6. return to consequences in play.

Do not replace these with business-document structures such as `Executive Summary`, `Recommendation`, `Assessment`, `Key Takeaways`, or `Implementation Plan` unless the document is explicitly a meta planning document.


## Source Prose Preservation and Promotion

Source prose is not merely provenance. When source-material prose is promoted into the main corpus, preserve the source paragraph chain unless it is factually obsolete, duplicated by a stronger manuscript passage, or explicitly superseded by later canon.

The source paragraph chain is the sequence by which the manuscript explains a subject. It may move from event to cause, from cause to consequence, from consequence to institutional response, and from institutional response to play use. This chain is often the author's actual voice. Do not replace it with a table row, terse summary, or neutral capsule merely because the facts can be extracted.

Tables may summarize source prose. Tables must not replace source prose where the prose explains:

- why an event happened;
- what changed because of it;
- who benefited;
- who was harmed;
- who regulated, controlled, resisted, exploited, or profited from it;
- what ordinary people believed about it;
- what the Referee, GM, player, or campaign should do with it.

This rule applies especially to histories, nations, institutions, cultures, wars, disasters, technologies, species, religions, economies, crimes, and social conditions. These subjects should normally have a prose carrier paragraph before any lookup table.

A table row may hold a date, quick reference, value, category, or comparison point. It should not be the only surviving home for the author's explanation. If the original source has a paragraph that teaches the reader why the item matters, the primary corpus file should carry that paragraph or a close revision of it.

### Minimal-Intervention Source Prose Rule

When user-provided source prose contains a usable narrative, explanation, argument, image, judgment, or event sequence, preserve it as closely as possible during promotion into the corpus.

Editors may correct spelling, punctuation, grammar, obvious typos, duplicated words, malformed sentences, inconsistent capitalization, and local word choice when those corrections make the prose clearer. Editors may also repair continuity errors when later canon requires it. These corrections should be close edits. They should not become a paraphrase pass.

Do not summarize, compress, flatten, or replace the author's prose merely because the facts can be stated more efficiently. Do not convert a vivid source passage into a neutral capsule unless the target file is explicitly a quick reference. Preserve the paragraph chain, emotional cadence, cause-and-effect movement, named images, local turns of phrase, and unusual but intentional wording whenever they remain compatible with canon.

If the source prose is too rough for direct promotion, revise it by close editing first. Recompose only when close editing cannot make the passage usable, when later canon supersedes the passage, when the passage duplicates a stronger manuscript treatment, or when the target document has a different reader task that truly requires compression.

A good close edit removes friction without removing the author. A bad close edit extracts facts and leaves generic corpus prose behind.

### Prose First, Table Second

For narrative history, institutional explanation, culture, law, technology, and setting consequences, use prose first and table second unless the source itself is already a table or catalog.

The preferred order is:

1. introduce the topic in prose;
2. preserve or revise the source paragraph chain;
3. provide the chronology, table, list, or quick-reference aid;
4. add local notes only where the table cannot carry the needed meaning;
5. cross-reference the primary home rather than scattering the explanation across many files.

This does not prevent timelines. Timelines are useful. The problem is a timeline that becomes the only version of the history.

### Preserve Cause-and-Effect Sentences

Treat cause-and-effect sentences as high-value material. Sentences using phrases such as `as a result`, `this allowed`, `this caused`, `following`, `because`, `however`, `in return`, and `at the same time` often carry the logic of the setting.

Do not remove these merely to make the text shorter. Remove or revise them only when the sentence is wrong, duplicated, confusing, or clearly a generated filler sentence rather than source-manuscript reasoning.

### Source Promotion Review

When converting `_source-material/*.txt` or other source notes into a primary corpus file, perform a source-promotion review.

Ask these questions before the file is considered incorporated:

- Did any explanatory paragraph become only a table row?
- Did a causal sequence become a date list?
- Did the source explain what the event meant, while the corpus file only states that it happened?
- Did the source's connective language get removed even though it guided the reader through the logic?
- Did a vivid authorial passage become a neutral summary even though close editing would have worked?
- Can a reader still learn what happened, why it happened, who was affected, who responded, and what it means for play?
- Is the original voice preserved in the primary home, or only archived in a provenance appendix?

If the answer shows voice loss, restore prose to the primary file. The appendix may retain the raw source, but the main corpus must still teach the topic in the author's prose style.

### No Appendix Exile

A source appendix is useful for audit and provenance. It is not a substitute for incorporation.

Do not exile the best source prose into an appendix while leaving the main corpus as a clean index of extracted facts. The appendix may preserve the raw source exactly. The primary home must still carry the strongest prose needed for a reader to understand the subject without recovering the author's meaning from archival material.

## Sentence Rhythm and Connective Language

Do not over-correct the authorial cadence. The source manuscripts often use plain connective language to keep the reader oriented.

Common acceptable phrases include:

- `As a result, ...`
- `However, ...`
- `In return, ...`
- `At the very least, ...`
- `The Referee should ...`
- `The GM should ...`
- `The player should ...`
- `It is possible that ...`
- `It is likely that ...`
- `This is because ...`
- `This allows ...`
- `These are ...`
- `Here are ...`
- `See the section on ...`

These are not defects by default. Remove them only when they are repetitive, ambiguous, or obviously produced by machine filler.

The manuscripts also often use semicolons, parenthetical glosses, short explanatory asides, and examples following an em dash. Preserve these when they clarify terms or match the local section.

## Rules Presentation

Rules should read as instructions for use at the table or during character creation. They should not read like database records unless the section is actually a table, list, or catalog entry.

### Player-Facing Rules Language

Core rules should be written for use by players, teenagers, and younger readers at the table. A rule may be exact without sounding like a research paper, white paper, software specification, or consultant memo.

Use plain game words first:

- `add`;
- `subtract`;
- `roll`;
- `mark`;
- `record`;
- `gain`;
- `lose`;
- `spend`;
- `recover`;
- `round down`;
- `compare`;
- `target number`;
- `bonus`;
- `penalty`;
- `damage`;
- `injury`;
- `stress`;
- `weariness`;
- `HP`;
- `adjTN`;
- `DM`.

Avoid academic or LLM-favored abstraction in player-facing rules when an ordinary game word works. Do not use words such as `register`, `pressure`, `vector`, `modality`, `operationalize`, `ontology`, `payload`, `framework`, `axis`, `substrate`, `interface`, `regime`, or `workflow` merely to sound precise.

These words are not banned from the corpus. Some of them may be proper setting, scientific, or meta-design terms. They should not appear in the first explanation of a combat rule, character-creation rule, dice rule, injury rule, advancement rule, or player-facing table procedure unless the term is already a named SH44SER or DXD game term.

Bad player-facing rule:

```text
Weariness Pressure is the Target Number Modifier caused by the character's current Weariness Level.
```

Better player-facing rule:

```text
Weariness makes tests harder.

Add the character's Weariness Level to the Target Number.
```

Bad player-facing rule:

```text
The Referee should operationalize the consequence vector as a persistent character-state payload.
```

Better player-facing rule:

```text
The Referee should choose where the consequence goes.

Record the Scar against a Mental Quirk, Complication, Wealth source, or Network.
```

A technical term may be introduced after the ordinary rule is clear. Do not make the reader learn a technical label before learning what to roll, add, subtract, mark, or record.

A rule normally needs these parts:

- **Actor:** Who performs or controls the rule? Referee, GM, player, character, NPC, organization, or system.
- **Trigger:** When does the rule happen?
- **Default:** What normally happens?
- **Cost or Roll:** What is spent, rolled, assigned, compared, or checked?
- **Result:** What changes afterward?
- **Record:** What must be written down?
- **Limit:** What prevents abuse or confusion?
- **Example:** How does it look when used?

Do not hide the actor. SH44SER frequently says `The Referee should decide`, `The player must decide`, `Characters may`, or `The Referee may devise`. That direct assignment of responsibility is part of the rules presentation.

### Optional Rules

When a rule is optional, say so plainly near the beginning of the section.

Preferred forms:

- `This is optional.`
- `This rule is optional.`
- `The Referee may allow this rule when ...`
- `The GM should introduce this only when ...`

Do not turn optional rules into tentative prose. Optional does not mean vague. It means the Referee or GM chooses whether the rule is active.

### Defaults and Exceptions

State the default before the exception.

Good order:

1. what normally happens;
2. who decides;
3. what changes the default;
4. what the player records;
5. example.

Avoid leading with edge cases. Avoid introducing three exceptions before the reader knows the ordinary rule.

### Costs, Awards, and Records

When a rule touches SAP, XP, PRP, Wealth, DM, TN, Stress, Fatigue, Scar points, Bonds, Leverage, or any durable feature, state what is recorded.

Use plain instruction:

- `Record the value on the character sheet.`
- `Note the Margin-of-Failure.`
- `Assign one Leverage Type from the list and note the TN.`
- `At the end of the session, discard all tokens.`
- `The Referee should decide the XP Conversion Rate.`

Record-keeping is not secondary. It is part of the design voice.

### Examples

Use examples as applied rules. The source manuscripts commonly use `Example —` and then a concrete calculation or situation. Preserve that pattern.

Examples should usually do one of these:

- show a calculation;
- show a Referee or GM decision;
- show a player choice;
- show how an exception works;
- show what gets recorded;
- show what consequence follows;
- show how a formula behaves with actual values;
- show how a player's narration changes the mechanical result.

Avoid examples that are merely cinematic. If an example is narrative, it should still clarify a rule.

Preferred format:

```text
Example — A character has 10 SAP in Holdings worth 20,000 Pd. This character may claim to “bank-roll” any item worth 200 Pd or less.
```

Do not replace this with a detached sidebar unless the corpus format calls for sidebars.

### Examples Are Often Rules

Do not treat examples as decorative prose. In SH44SER and DXD, examples frequently explain how the rule actually behaves. Removing the example can remove the reader's only local demonstration of how to use the rule.

Keep examples when they show:

- what gets rolled;
- what gets recorded;
- how DMs are gathered;
- how dice are flattened;
- how a Referee or GM awards or withholds a bonus;
- how a player can offer a justification;
- how an exception works;
- how an abstract rule becomes a table-ready result.

The example may be short. It may also be long when the rule requires several steps. Do not trim examples only because they repeat part of the surrounding rule. A good example often repeats the rule in the form that the player or GM will actually use.

## Mathematical and Mechanical Repetition

Mechanical repetition is not automatically redundancy. SH44SER and DXD are manuals meant to be used while designing characters, resolving scenes, building equipment, running combat, or adjudicating downtime. If the reader must calculate something at that point in use, the relevant formula or table-use instruction may need to appear there, even if it is also defined elsewhere.

### Repeat Math Where It Is Used

Do not treat every repeated formula, equation, or calculation rule as bad duplication. In SH44SER, repeated math is often good manual design when it appears at the point where the reader is expected to actually use it.

This is most true inside game-mechanics writing, especially for:

- table-ready play procedures;
- downtime procedures;
- design-time or build-time procedures.

Prefer this standard:

- repeated concept prose: usually trim;
- repeated lore summary: usually trim;
- repeated formulas in active mechanical contexts: often keep;
- repeated formulas in passive setting prose: usually trim.

Repeat a formula locally when:

- the reader is expected to calculate something in that section;
- the formula is hard to memorize;
- forcing a cross-reference would slow down ordinary use;
- the local restatement supports a distinct procedure, worksheet, or table task.

If a repeated formula is kept, keep the surrounding explanation concise and let the local procedure be the reason for the repetition.

### Formula Presentation

A formula should usually be introduced before it is used, then followed by at least one applied example when the calculation is important.

No bare formulae. Every formula needs a short lead-in unless the document header or immediately prior section already established the terms used in the formula. The lead-in should state what the formula finds and define any non-obvious abbreviation.

Preferred order:

1. state when the formula is used;
2. state who uses it;
3. state what the formula finds;
4. identify abbreviations or terms not already established;
5. state the formula;
6. explain rounding or lookup instructions;
7. give a short example;
8. provide a table if the formula is frequently consulted.

Common repeated abbreviations may remain compact after the reader has seen them often enough in SH44SER. `adjTN` and `HP` are acceptable because they recur across multiple documents and are usually easy to parse. Less common abbreviations, single-letter variables, table-call terms, and local shorthand must be introduced before use.

Prefer human-readable formulae in the main rule. Compact notation may follow when useful for quick reference, character sheets, worksheets, or later balancing.

Good formula presentation:

```text
Damage Level is the percent of total HP already lost. Round down after multiplying by 100.

Damage Level = floor(HP Lost / Maximum HP × 100)
```

Good formula presentation with common notation:

```text
Weariness makes tests harder.

Add the character's Weariness Level as an adjTN.

Formula: adjTN = +Weariness Level
```

Avoid formulae that appear before the reader knows what they are calculating:

```text
Damage_Level = floor(Current_HP_Lost / Max_HP × 100)
```

Do not convert manuscript-style formulas into abstract algebra unless the source already does so. Preserve practical notation such as:

- `TN=7+`;
- `DM +1`;
- `DM -1D`;
- `2D`;
- `3D`;
- `XD`;
- `IM`;
- `PML`;
- `Max Advantage = 1 + (PML – 1)/3`.

The rules are meant to be read by a Referee, GM, or player during use. They are not written primarily for a programmer, mathematician, or database parser.

### Compact Catalog Entries Are Allowed

Catalog entries may be compact. A Trait, Skill, Spell, item, weapon, armor, denizen, Power, Special Ability, or equipment entry may use a compressed local structure when the reader is expected to scan many entries.

Preserve entry syntax such as:

- name;
- rating or level;
- keyword line;
- mechanical effect;
- limits;
- cost;
- prerequisite;
- cross-reference.

Expand only when the entry is confusing, when the effect has consequences that require explanation, or when the entry is being promoted from a catalog note into a full rule section. Do not force every catalog entry to become a long teaching paragraph.


## Referee and GM Guidance

Referee guidance in SH44SER should be direct and operational. It should tell the Referee what to prepare, decide, track, reveal, arbitrate, award, restrict, or reconcile. It should not be written as generalized facilitation theory.

The Referee is not merely a narrator. The Referee is an arbiter, note keeper, world-builder, rules interpreter, role-player of NPCs, coordinator of players, and final decision-maker. The Referee’s decision should be fair and internally consistent because future play may rely upon that decision.

A good SH44SER Referee-facing passage often includes:

- the task the Referee performs;
- the reason the task matters;
- how players are affected;
- what notes or records are needed;
- what future consequence follows;
- what the Referee may alter, simplify, or decide.

Use direct language:

- `The Referee should keep notes ...`
- `The Referee should award ...`
- `The Referee may decide ...`
- `The Referee needs to decide ...`
- `The Referee and the players together can shape ...`

Do not use corporate or theory language in place of this. Avoid `stakeholders`, `content moderation`, `session facilitation framework`, `engagement loop`, `narrative economy`, or `fiction-first procedure` unless quoting some external game theory on purpose.

For Sarna Len / DXD, use `GM` and preserve its teaching-forward structure. The GM introduces the game, describes useful information, tracks what was said, provides prompts, and gradually introduces mechanics. Use that language rather than SH44SER’s Referee register.


### GM Permission and Player Offers

DXD frequently uses a negotiated table pattern. The GM decides, but players may suggest Skills, Traits, Cues, Hooks, narrative descriptions, tools, situational details, or other justifications. Keep that procedure visible.

Do not rewrite such rules as though the GM silently computes every modifier. The player may describe the attempt, name relevant Traits or Skills, suggest a narrative cue, or explain why a bonus applies. The GM then allows, limits, rejects, or adjusts the application.

This pattern should be written directly:

- `The player may suggest ...`
- `The GM should allow ... if it is reasonable.`
- `The Referee may approve ...`
- `If the Referee agrees ...`
- `The GM may award DM +1 to DM +3 ...`

This preserves the source style where character details, emotional cues, social context, tools, and narration can matter mechanically, but the GM or Referee remains the arbiter.

### Dice Transparency in DXD

DXD favors public-facing dice rolls. Hidden rolls and Partial Information rolls are allowed, but they are exceptions and should be treated carefully because they can create paranoia or derail the narrative.

When writing or revising DXD rules, usually identify:

- who rolls the dice;
- whether the roll is public;
- whether the GM keeps the TN hidden;
- when the result is revealed;
- why secrecy is useful in that circumstance;
- what risk secrecy creates for player trust.

Do not normalize hidden GM rolling as the default DXD presentation. In Narrative situations, the GM should normally allow players to roll dice for their own characters. Technical Combat may use both GM and player rolling for their respective characters or NPCs.

## Player-Facing Guidance

Player-facing text should tell players what they control and what they are expected to do. It should not over-explain Referee-only concerns.

Good player-facing guidance:

- tells the player what choices are available;
- tells the player what to record;
- tells the player what the choice means in play;
- warns when a choice creates difficulty;
- identifies where Referee approval is required.

Avoid hiding limits because they may disappoint players. The source prose is comfortable saying that some choices are difficult, dangerous, restricted, or better reserved for veteran players.

## Lore Presentation

Lore should not be written as an encyclopedia entry unless the section is an almanac or database entry. SH44SER lore usually explains how the world got this way and what that means for institutions, ordinary citizens, criminals, heroes, nations, and Referees.

Use this order when it fits:

1. state what the subject is;
2. place it in time, society, institution, or geography;
3. explain its causes;
4. explain how people respond to it;
5. explain the consequence for play or future setting movement.

A SH44SER setting section should usually answer at least one of these:

- Who benefits?
- Who is harmed?
- Who regulates it?
- What does the WPC, TechnoPol, SecDuty, a GOB, or a local government do about it?
- What does the public think it means?
- What trouble does it create for the Referee?
- What does a player-character encounter because of it?

Sarna Len lore may instead answer:

- What ancient thing caused this?
- What named peoples or beings are involved?
- What danger remains?
- What does civilization believe about it?
- What do adventurers risk by approaching it?
- What does the GM use it for?

## Moral and Legal Language

Do not flatten SH44SER’s moral vocabulary. The corpus can distinguish moral judgment, legal status, political classification, and public attribution.

It is acceptable and often necessary to use terms such as:

- exploitation;
- slavery;
- murder;
- sophonticide;
- corruption;
- authoritarian;
- toxic society;
- oppression;
- abuse of power;
- criminal endeavor;
- justified force;
- legal process;
- law-breaking;
- vigilantism.

Do not replace moral clarity with vague neutral language when the setting subject is meant to be contemptible or socially destructive. Also do not collapse legal status into moral status. SH44SER often requires the Referee to keep both in view.


## Direct Safety and Subject-Matter Guidance

When writing safety or subject-matter guidance for DXD or SH44SER, use direct table language. Say what the GM or Referee should do. Do not replace this with institutional language such as `content policy`, `safety framework`, `stakeholder comfort`, or `risk management posture` unless the document is explicitly a meta-policy document.

The source style is plain:

1. identify the difficult subject;
2. state that it may be uncomfortable;
3. tell the GM or Referee to exclude, alter, warn, or manage it;
4. return to how the subject functions in the game-world or at the table.

This is especially important for sections dealing with abuse, exploitation, slavery, systemic inequality, prejudice, sex and gender, war, coercion, children, trauma, or other difficult material. Do not make these sections coy. Do not bury the practical instruction.

A Sarna Len section may say directly that the GM should not abuse players and that uncomfortable topics may be excluded, added to, or modified for game-play. A SH44SER section may similarly tell the Referee to set boundaries, warn players, or decide how much of a topic belongs in the active campaign.

## Technical and Scientific Language

The author uses technical language, but the best passages anchor it in concrete effects. Do not replace named world terms with generic abstraction.

Use the setting term when the setting term exists. Explain it locally if the section needs it.

Prefer:

- `Trans-Scan` over `matter transmission system` after definition;
- `Formian Enclave` over `alien settlement unit`;
- `Pseudodollar medallion` over `secure financial device` when the specific item matters;
- `Frame Parallel` over `alternate-reality topology` unless the technical explanation is genuinely about topology;
- `Mustrum`, `picoswarms`, and `hamerbridges` in Sarna Len/DXD rather than generic magic-energy abstractions.

Generic words such as `mechanism`, `framework`, `vector`, `axis`, `substrate`, `interface`, `topology`, `signal`, `coherence`, and `regime` are not banned from technical or setting explanation. Use them only when they do real explanatory work. Do not use them as automatic connective tissue.

Keep a hard distinction between technical explanation and player-facing rule instruction. A Formian biology section, MEST explanation, or Trans-Scan theory section may need technical words. A combat-injury rule, damage rule, XP rule, equipment-use rule, or character-sheet procedure usually does not. In those sections, prefer `add`, `subtract`, `roll`, `gain`, `lose`, `mark`, `record`, `bonus`, `penalty`, `level`, `damage`, `injury`, `stress`, and `weariness`.

A good technical section does this:

1. gives the named thing;
2. explains what it physically or socially does;
3. gives the consequence;
4. only then offers the compressed technical summary.

## Headings

Headings should follow the local manuscript pattern. They are often brief and practical.

Common useful headings:

- `OVERVIEW`
- `CONSIDERATIONS`
- `PROCEDURE`
- `MANAGEMENT`
- `REQUIREMENTS`
- `DEFINITIONS`
- `EXAMPLE`
- `Assign [Thing]`
- `Handling [Thing]`
- `Of [Subject]` in Sarna Len genre sections

Do not convert all headings into SEO-like explanatory headings. Do not add clever titles unless the manuscript section already uses that style.

A parent heading may need a short orienting paragraph, but do not impose this mechanically. Some sections in the manuscripts stack headings because the table layout and local context make the structure clear. Add orientation when it improves use; do not add filler just to satisfy a rule.

## Lists and Bullets

Use lists when the material is a list of entries, steps, examples, conditions, awards, or options. Keep list lines close. Do not turn every explanatory paragraph into bullets.

Use bullets for:

- rule options;
- XP awards;
- table notes;
- named examples;
- classifications;
- checklists;
- short procedural steps.

Use numbered lists for:

- ordered procedures;
- priority ladders;
- step-by-step creation instructions;
- sequences where order matters.

Prefer paragraphs for:

- lore explanation;
- moral or legal interpretation;
- setting consequences;
- background rationale;
- Referee reasoning that is not a checklist.


### Indented Lists and Nested Procedure Structure

Use indents when the source rule uses a local hierarchy that matters for play. Do not flatten nested source material into one paragraph merely because the facts can be summarized. If a rule has a main action, sub-actions, costs, examples, exceptions, and Referee or GM rulings, preserve that visible structure unless it is confusing or obsolete.

Indented lists are useful when the reader must see that one item belongs under another item.

Use nested bullets for:

- examples that belong to a rule;
- sub-options under an action;
- costs attached to a choice;
- Referee permissions or limits attached to a declaration;
- results under a pass or fail outcome;
- special cases under a general rule;
- XP awards under a reward rule;
- status effects under a combat condition;
- record changes under a consequence.

Use ordered lists when the steps must happen in sequence.

Use unordered lists when the entries are options, examples, conditions, awards, or parallel effects.

Do not over-flatten this structure. A flattened paragraph may read smoothly, but it may hide the order in which the Referee, GM, or player must use the rule.

Preferred structure:

```text
The player declares the action.

1. The Referee identifies the action family.
2. The Referee names the Test, if one is needed.
3. The player rolls.
4. The Referee applies the result.
5. Record any lasting consequence.

On success:

- apply the immediate result;
- record the condition if it lasts beyond the exchange;
- award XP if the rule says to award XP.

On failure:

- apply the failed result;
- record any cost already paid;
- apply a complication if the failure changes the scene.
```

Do not rewrite that structure as:

```text
The player declares the action, the Referee identifies the family, names the Test, the player rolls, and then the Referee applies the result and records the consequence, with success or failure changing the result as appropriate.
```

The second version may be shorter, but it is worse as a rule because it hides the procedure.

### Preserve Source List Shape

When source prose already uses a list, ordered sequence, example block, indented sub-list, or table-local note, preserve that structure unless there is a clear reason to change it.

Editors may correct typos, grammar, syntax, capitalization, local term drift, and internal consistency. Editors may convert a run-on list into bullets when that makes the rule easier to use. Editors should not convert a useful list into paragraph prose merely to make the section look more polished.

This matters especially for:

- action procedures;
- combat actions;
- grappling;
- Breaking Free;
- Compromised Status;
- Showing Off, Flair, and Flourish;
- Hasty Actions;
- Initiative procedures;
- Power use;
- Power Stunts;
- XP awards;
- Referee Guidance;
- `For example` blocks;
- equipment use;
- conditions and statuses;
- optional rules.

When a source section has a main rule followed by examples, keep the examples under that rule. Do not move them into a detached example appendix unless the target file is only a quick reference.

### Examples Under Rules

Examples should usually remain indented under the rule they teach.

A `For example` block is often Referee Guidance or GM Guidance. It may show what the Referee should allow, what the player must describe, what penalty applies, what XP is awarded, what gets recorded, or what consequence follows.

Preferred form:

```text
Showing Off is optional.

The player declares that the character is Showing Off before a meaningful Test. The player adds a visible constraint that makes the action harder, riskier, slower, more public, or less efficient.

- Each approved constraint applies DM -3 to the Test.
- Each approved constraint awards +10 XP if the Test matters.
- The Referee should not award XP for description that does not change risk or difficulty.

For example:

- A character attacks while running backward.
- A character monologues instead of taking the safest opening.
- A character telegraphs an attack to humiliate the opponent.
- A character performs needless acrobatics where ordinary movement would be safer.
```

The example list is not decorative. It teaches the Referee what qualifies.

### Nested Referee and GM Guidance

Referee Guidance or GM Guidance may be placed directly under the rule it modifies. It does not always need a separate heading.

Use a nested guidance note when the guidance is local:

```text
The character may attempt to break free.

- On success, remove two Immobilized levels.
- If all Immobilized levels are removed, the character receives a Bonus Action.
- The Bonus Action is normally used to step away.

Referee Guidance:

- Allow additional arms or legs to assist when the anatomy or position supports it.
- Apply Fatigue for each limb used in this way.
- Do not allow a limb to assist if it is pinned, restrained, injured, or unavailable.
```

Use a separate heading only when the guidance applies to the whole section or multiple procedures.

### Indentation for Pass, Fail, and Record

When a rule has different outcomes, use visible substructure.

Preferred form:

```text
On pass:

- the character performs the action;
- remove the listed condition;
- record any XP, Fatigue, Stress, or status change.

On fail:

- the action fails;
- costs already paid remain paid;
- the Referee may add a complication if failure changes the scene.
```

Do not combine pass and fail results into one dense paragraph when the player, Referee, or GM will need to consult the rule during play.

### Indentation for Optional Rules

Optional rules should still be written firmly. Use the first line to state that the rule is optional, then give the procedure.

Preferred form:

```text
This rule is optional.

The Referee may open Hasty Actions when high-capability action should create extra AP and extra bookkeeping.

Use this order:

1. The player declares Hasty Action use.
2. The player spends the required DEX DM, STA DM, or both.
3. The character gains the listed AP.
4. Record Fatigue.
5. Reduce the spent Prime Requisite DMs until the next Initiative.
```

Optional does not mean vague. Optional means the Referee or GM decides whether the rule is active.

### Do Not Create False Outline Structure

Do not add indentation merely to make prose look organized. Use it when the hierarchy helps the reader use the rule.

Avoid this:

```text
- The city has laws.
  - Laws are important.
    - People may break them.
      - The Referee should care.
```

Use prose instead:

```text
The city has laws because public authority still matters. A character who breaks those laws may create evidence, license trouble, lawsuits, police attention, or institutional pressure. The Referee should record only the consequences that survive the scene.
```

Lists are for usable structure. Prose is still preferred when the section is explaining cause, setting, institution, public reaction, moral consequence, or legal consequence.



### Post-table Notes and X Definitions

When a table contains a Skill, Trait, Talent, Tag, Power, Disability, price formula, rating formula, armor formula, or any other rule entry involving `X`, do not rely on the table cell to teach the rule. Tables are for lookup. Rules are learned in prose.

After the table, provide a **Notes** block that defines every local `X`, abbreviation, formula term, and overloaded word used in the table.

Use this structure when any table has math:

```text
Notes:

- `X` in `Impact X` is the number of 10-point AR steps reduced by the attack.
- `X` in `Pierce X` is the number of Hardened levels reduced by the attack.
- `Hn` means Hardened n; `H2` means Hardened 2.
- `AR` means Armor Rating and may be any integer. Do not round AR to preferred values unless the active subsystem says to round for table speed.
```

Use this structure when any table has Skill, Trait, Talent, Tag, Power, or Disability entries:

```text
Notes:

- A Skill uses LoM as its ordinary DM when the Skill directly applies.
- A Trait is a durable levelled feature. `X` is the purchased or assigned level.
- A Tag is not levelled. If a tag needs a number, write a statistic or Trait instead.
- A Disability that awards or refunds points must state when it enters play and what record changes when it does.
```

Do not place the only explanation of a rule inside a table cell. If a table cell must be compact, put the full description after the table. This applies especially to materials, armor, weapons, ammunition, Powers, Power Tags, Traits, Talents, Skills, Disabilities, and any entry using R30, R125, AR, OR, Hn, DM, TN, LoM, SAP, PRP, or XP.

### Importing Source Material with Lists

When importing from SH44SER, DXD, Sarna Len, or user-provided source notes, perform this check before rewriting:

1. Does the source use an ordered list?
2. Does the source use bullets?
3. Does the source place examples under a rule?
4. Does the source place Referee or GM advice near a specific rule?
5. Does the source show pass, fail, award, cost, or record as separate items?
6. Would flattening the list make the rule harder to use?
7. Would moving the examples remove the local Referee or GM guidance?

If the answer to any of these is yes, preserve the list shape or improve it with close editing. Do not summarize it away.

## Tables

Tables are useful when the reader compares repeated structured data. They are not required for every rule.

Use tables for:

- costs;
- ranks;
- age groups;
- TN schedules;
- XP awards when repeated;
- equipment values;
- categories with fixed awards;
- timelines;
- comparative classifications.

A table should usually have a short lead-in sentence. Table-local notes should remain near the table. Use simple local markers if needed.

Do not bury the actual rule only in a table. State the operational rule in prose, then provide the table.

Do not bury the actual history, setting explanation, institutional logic, or cultural meaning only in a table. State the explanatory prose first, then provide the table as a lookup aid. A table can preserve facts while still destroying voice.



### Post-Table Notes for X Values and Math

Do not leave the only explanation of a Skill, Trait, Talent, Tag, Power, Disability, AR value, OR value, LoM value, SAP cost, PR value, or other `X` notation inside a table cell. Tables are good lookup aids, but a table cell is a poor primary home for a rule definition.

After a table that uses mathematical shorthand, provide notes that define every active shorthand used by the table. This applies especially to `X`, `Hn`, `AR`, `OR`, `ORa`, `LoM`, `SAP`, `PRP`, `DM`, `TN`, `Impact X`, `Pierce X`, `Hardened X`, `Armor X`, `Damage`, and any bracketed or colon notation.

Use source prose where possible. If the source explained a table column after the table, preserve that explanation near the table. Do not let the table be the only place where the reader learns what a value means.

### Preserve Probability and Lookup Tables

DXD uses probability tables and lookup tables as teaching aids, not merely as appendices. Do not remove or relocate them only because they are large. A probability table may be part of the GM's ability to judge whether a Test is worth rolling, whether a TN is too low, or whether a situation needs additional complications.

Keep a probability or lookup table near the rule when:

- it changes Referee or GM judgment;
- it teaches the practical scale of a mechanic;
- it supports difficulty setting;
- it prevents accidental misuse of DMs, TNs, Bonus dice, Penalty dice, or Base dice;
- it lets a player understand why a choice matters;
- it reduces page-flipping during character creation, combat, downtime, or advancement.

A table may be duplicated in a quick-reference section, but the operational copy should remain near the rule that explains it. If the table is very large, give it a short local introduction and keep the table-local notes with it.

## Capitalization and Terms

Preserve established capitalization. SH44SER and DXD often capitalize terms that are ordinary English words when those words are game terms.

Examples include:

- Referee;
- Player;
- Player Character;
- Prime Requisite;
- Special Ability;
- Complication;
- Mental Quirk;
- Planning Session;
- Skirmish Session;
- Storytelling Session;
- Test;
- GM;
- Trade;
- Trait;
- Deity;
- Zed.

Do not normalize these into lower-case prose merely because a conventional style manual would do so.

Use acronyms with the manuscript pattern: full term first, acronym or abbreviation in parentheses or brackets when helpful, then the abbreviation afterward.

Acceptable forms include:

- `World Peace Council [ WPC ]` when matching SH44SER house style;
- `GM` after `Game Master [ GM ]` in DXD;
- `DM` and `TN` after the local rule has established them;
- parenthetical glosses such as `Universal Personhood Identifier` or `casualty evacuation` when the section needs them.

## Examples of Source-Like Rule Flow

A new SH44SER rule should usually resemble this pattern rather than a policy memo.

```text
SCARS
This is optional.

A character may acquire a Scar when a player chooses to reduce an immediate burden which would otherwise affect the current scene. A Scar is not a reward. It is a delayed consequence purchased into the character's existing problems, obligations, resources, or social position.

The player buys 1 Scar point for every 3 adjDM or adjTN of immediate burden removed. The Referee must approve the fiction which explains where that Scar goes.

Record the Scar against an existing Mental Quirk, Complication, Wealth source, or Network. If the player wants a new permanent Mental Quirk or Complication, spend 2 Scar points and use Referee approval.
```

The important traits are not the exact topic. The important traits are the order: optional status, definition, player choice, cost, Referee approval, record.

## Examples of Source-Like Lore Flow

A new SH44SER lore section should usually begin with direct setting truth, then consequence.

```text
The Geo-political Tension Enforcement Routing Schedule [ GTERS ] is the SecDuty clock for deciding where enforcement attention must go next. It does not predict virtue. It predicts how long the WPC believes it can wait before a Hostile, Enemy, or Neutral nation becomes a military, humanitarian, or Agreement-level crisis.

As a result, GTERS is both an operational tool and a political weapon. A nation placed on the Red Line will deny the rating, accuse the WPC of preparing aggression, and begin moving assets before SecDuty arrives.
```

The important traits are direct definition, institutional consequence, and world reaction.

## Cleanup Requirements

Cleaned documents should stand alone. The reader should not need to know the prompt, chat thread, or migration path that produced the file.

Remove:

- `USER` / `ASSISTANT` transcript markers;
- `Executive Summary` when the document is not a memo;
- `Recommendation` when the document is not an advisory memo;
- `Technical Assessment` when the document is a rule or reference entry;
- stale labels such as `legacy`, `handoff`, `alternate`, `obsolete`, or `proposed` when the value is settled;
- draft notes such as `Ideas to Integrate`, `Thread Consensus`, `Converted v`, `Consolidated v`, or `Document Status`;
- references to unseen conversation context;
- generic adventure hooks inside reference documents unless the document is explicitly for scenarios or Referee prep.

Do not remove gameplay consequence merely because it sounds like an adventure seed. A setting fact may remain if it explains how institutions, crimes, politics, or societies operate.

## Handling Unsettled Material

If a value is unsettled, say so directly. Do not preserve old branches as if they are equal canon.

Use:

- `This is under evaluation.`
- `The preferred current treatment is ...`
- `This remains a proposal until incorporated into the main rules corpus.`
- `The Referee may use this as an optional rule.`

Do not use:

- `legacy version` unless the document is explicitly historical;
- `alternate branch` unless the corpus needs to preserve alternatives;
- `possible refinement` in a final rules section;
- `the proposed system` after the system has been accepted.

## Refactoring Priorities

When improving a document, do this in order.

1. Preserve canon and mechanics.
2. Preserve authorial voice.
3. Preserve user-provided source prose through close editing before recomposition.
4. Preserve local structure where functional, including nested lists, ordered procedures, example blocks, and table-local notes.
5. Remove prompt and draft residue.
6. Clarify the actor, trigger, cost, result, record, and limit.
7. Improve presentation order only where the reader path is confused.
8. Trim duplication only when it does not harm table use.
9. Preserve local formulas, lookup tables, probability tables, and examples when they support active use.
10. Add examples only when they teach the rule or clarify the setting consequence.

Do not make the document shorter merely because shorter prose is easier to scan. SH44SER and DXD often use explanation as part of the rule.

## When to Split Files

Do not split files merely because a section is long. The manuscripts often prefer substantial chapters with internal headings. Split only when the reader task truly changes.

Split when:

- a design note is obscuring a live rule;
- a speculative appendix is being mistaken for canon;
- a scenario procedure has been mixed into a setting reference;
- a quick-reference table would clearly be more usable as a separate aid;
- source derivation material is too heavy for the main reader path.

When splitting, keep the main file as the authoritative reader path. Do not create many thin fragments that force the reader to chase the rule across files.

## Canon Ownership and Anti-Fragmentation

When one canon topic touches multiple files, assign one file as the **primary home** for that topic.

The primary home should carry the material a reader needs in order to actually learn the topic:

- the main definition;
- the local thesis or framing paragraph when it matters;
- the baseline rule, table, or metric set;
- the key examples or consequences;
- the default terminology and interpretation.

Other files may still do useful work, but their roles should stay narrower and clearer. In most cases they should be one of these:

- **local application** — a nation, bloc, species, or subsystem file using the canon for its own subject;
- **quick reference** — a table, list, or aid optimized for lookup;
- **appendix or method note** — derivation, benchmark math, or deeper support that would overburden the main reader path;
- **provenance** — source-material retained for comparison or audit.

Do not distribute one topic's core explanation so widely that no single file teaches it well anymore. A topic is not fully incorporated merely because fragments of it survive across many files. It is only meaningfully incorporated when its primary home can teach the subject without requiring recovery work from scattered descendants.

When revising a fragmented cluster, use this order:

1. identify the primary home;
2. restore the core explanation, table, and consequence chain there;
3. trim or narrow satellite files to their local task;
4. keep repeated math or tables only where active use requires them;
5. replace diffuse restatement with short local references where possible.

Quick-reference duplication is allowed when it genuinely helps table use. Silent co-ownership is not. If a narrower file needs to use a different figure, interpretation, or exception for a different question, it should say so plainly rather than silently replacing the baseline carried by the primary home.

### Shadow Ownership Prohibition

A satellite file may apply a term, but it must not quietly become a second primary home for that term.

When a file about a nation, incident, subsystem, technology, or cultural exchange needs a term such as Enclave, Prime Matron, Five Matrons, Sum of Man, Silmarrimis, Nephalimion, Gana-Peetu, Gestalt, Weirdling, or WPC, it should use the controlling definition from the primary home and then explain only the local consequence. Do not restate the baseline in a new tense, new table row, or local shorthand that can drift from the primary home.

A duplicate definition is allowed only when it is explicitly a quick reference or table-use aid. In that case, the file must name the primary home and must not add new meaning.

If a later source requires the baseline to change, revise the primary home first, then revise the satellite files. Do not let a local correction become a hidden competing canon.

## Addendum: Lower-Weight SH44SER Manuscript Observations

This addendum has lower weight than the source manuscripts, current user instructions, and the main sections of this style guide. It records useful patterns visible in the canon pre-iteration SH44SER manuscript. Use these observations when they fit the target document. Do not use them to decide the final corpus architecture, terminology policy, citation policy, end-note policy, or future repository layout.

These observations are especially useful when revising a SH44SER rules passage, a setting passage that still belongs near rules material, or a compiled-manuscript chapter. They are less useful when revising a narrow corpus reference file that has already been assigned a cleaner task.

### Source Preservation and Rationalization

SH44SER began as a reconstruction, expansion, and rationalization of older Superhero 2044 material. When a passage carries older-game texture, source lineage, or old-school rules assumptions, do not erase that merely to make the prose sound newer.

Preserve the source shape when it still works. Rationalize when a conflict, obsolete assumption, or rushed older ruling needs a cleaner explanation. The preferred move is not to replace the old material with generic modern RPG prose. The preferred move is to make the inherited material usable in SH44SER by clarifying its rule purpose, setting consequence, and Referee use.

This matters especially for:

- police-centric equipment and street-level procedures;
- inventory, budget, employment, and purchase rules;
- Inguria-derived setting material;
- old-school scenario and patrol assumptions;
- superhero, supervillain, and crime-fighting procedures;
- Saxman-era concepts that have been reinterpreted rather than discarded.

Do not over-modernize inherited terms unless the corpus has already replaced them. Do not preserve an older contradiction merely because it is old. Preserve the usable shape, then make the rule or setting statement work.

### The Golden Rule and Optional Complexity

SH44SER rules should not read as an inflexible legal code. The rules are meant to serve play. If a rule is unnecessary, too complex, or does not fit the needs of the group, the Referee and players may alter it, simplify it, improve it, or remove it.

This does not mean the rule should be written vaguely. Write the rule clearly first. Then state where the Referee may simplify, waive, replace, or ignore it. Optional complexity should be firm in presentation and flexible in use.

When a concept is uncomfortable for the table, the rules may tell the Referee to change it or drop it. Do not translate that into corporate safety language. Use direct table language. The purpose is to preserve play, not to preserve every uncomfortable element at any cost.

### Mode-Specific Writing

SH44SER does not use only one prose density. A compiled rules manuscript may contain setting explanation, Referee instruction, character creation, legal process, Skirmish procedure, Storytelling guidance, Planning procedure, optional tools, examples, and almanac material. These sections need not all sound identical.

Use the local mode to decide density and order:

- Storytelling guidance may explain narrative use and player-facing choices.
- Skirmish guidance may become more procedural, sequential, and exception-heavy.
- Planning and downtime material may need tables, worksheets, schedules, and repeated calculations.
- Legal and civic material may need institutional explanation before rule consequence.
- World Almanac material may use compressed setting entries, numbers, and local implications.
- Character examples and scenario examples may repeat rules in worked form.

This addendum does not decide whether such material remains in one compiled manuscript, becomes modular files, or is moved into another corpus arrangement. It only warns that when such material is present, the prose should match the local reader task rather than being flattened into one reference voice.

### Numerical Worldbuilding as Verisimilitude

SH44SER often uses numbers to make the setting governable and playable. Population, crime rates, police ratios, military force counts, incarceration rates, energy generation, GDP, income, equipment costs, power output, movement rates, and scaling indexes are part of the worldbuilding method.

Do not treat these numbers as trivia by default. Keep them when they support:

- Referee calculation;
- patrol or crime resolution;
- institutional scale;
- logistics;
- legal or economic consequence;
- equipment and infrastructure plausibility;
- comparison among nations, cities, organizations, or technologies.

If a number appears wrong, stale, or inconsistent, do not simply delete it. Prefer to correct it, qualify it, or move it to the correct table or appendix. If the number no longer supports play or setting logic, then it may be trimmed.

### Rhetorical Thesis Paragraphs

SH44SER sometimes uses a strong thesis paragraph to establish the moral, technological, or campaign meaning of a chapter. These passages may speak about hope, future shock, the burden of power, the social cost of technology, the importance of crime-fighting, or the way institutions fail and recover.

Do not automatically flatten these passages into neutral encyclopedia prose. Keep a thesis paragraph when it establishes:

- the campaign premise;
- the intended emotional or moral contrast;
- why the rule exists;
- why the setting is unstable;
- what the Referee should emphasize in play;
- what kind of superhero or supervillain story the section supports.

Trim only when the thesis repeats a point already made nearby, drifts into unrelated commentary, or no longer matches accepted canon.

### Compiled Manuscript Versus Modular Corpus

The canon pre-iteration SH44SER manuscript is a compiled rulebook. A compiled rulebook may place setting, rules, optional procedures, examples, tables, almanac entries, and Referee tools near one another because the reader is moving through a single game text.

A modular corpus may need cleaner separation. A setting-reference file should not absorb unrelated scenario procedure merely because the compiled manuscript once placed those materials near each other. A rules file may need to preserve a setting explanation only when that explanation teaches the rule, establishes a necessary assumption, or prevents misuse.

Therefore, when revising SH44SER material, first determine the target document type:

- compiled manuscript chapter;
- modular setting reference;
- modular rules addition;
- Referee procedure;
- player-facing rule;
- optional tool;
- almanac or database entry;
- example or scenario document.

Then revise toward that task. Do not force all manuscript material into standalone reference prose. Do not force all modular corpus files to retain compiled-manuscript adjacency.

## Common LLM Errors

Avoid these errors.

### Over-Flattening

Bad cleanup removes the author and leaves generic rules prose. Preserve the local rhythm where it teaches or frames the subject.

### Over-Paraphrasing Source Notes

Bad source promotion treats rough source prose as a fact pile. It extracts names, dates, and conclusions while discarding the author's sentence order, escalation, images, and emotional pressure. Correct the prose first. Only summarize when the target file is a quick reference, when the passage is obsolete, or when close editing cannot make the passage usable.

### Flattening Rules, Examples, and Lists

Bad cleanup turns a usable rule into a paragraph summary. It removes pass and fail structure, hides costs and records, and separates examples from the rule they teach.

If the source section uses bullets, numbered steps, an indented example, or a `For example` block, assume the structure is part of the rule until proven otherwise. Preserve it through close editing.

### Hiding the Actor

Bad rule prose says `Leverage is tracked` without saying who tracks it. Say whether the player, Referee, GM, character, organization, or system tracks it.

### Removing Consequence

Bad lore prose states facts without showing why anyone cares. SH44SER usually wants the consequence.

### Turning Rules into Policy

Bad Referee prose sounds like administrative policy. A Referee-facing section should tell the Referee what to do in play.

### Making Canon Sound Optional

Bad cleanup leaves `could`, `would`, or `proposed` in settled material. If it is canon, state it.

### Defensive Refutation Chains

Bad generated corpus prose sometimes begins settled lore with a chain of negative claims: `This document does not claim...`, `This does not mean...`, or `Do not read this as...`. This is usually chat residue. It makes the text sound like it is apologizing for the canon instead of teaching the reader what is true in the setting.

Use one positive default statement first. Then state the necessary limit once.

Bad cleanup:

```text
This document does not claim that most aliens look Human. It does not claim that most aliens can share Human environments. It does not claim that most aliens can be intimate partners for Humans.
```

Better corpus prose:

```text
Most alien life remains alien. Ash-and-Dream concerns the smaller subset of Class II life which becomes chemically readable, environmentally tolerable, socially legible, or physically compatible with Human beings. These are separate gates, and passing one gate does not prove passage through the next.
```

Use negative clarification only when correcting a likely table problem, dangerous misreading, or explicit canon boundary. Do not use negative clarification as the ordinary way to introduce settled canon.

### Aphoristic Signpost Phrases

LLM prose often uses short declarative signposts to simulate certainty: `That is the important boundary`, `That is the key move`, `This is the cleanest version`, `The final layer is...`, `X still matters`, or `Y is a high-filter exception`. These phrases are useful in chat because they tell the user where the assistant is placing emphasis. They are usually weak in corpus prose because they name the assistant's interpretation rather than teaching the setting.

Replace these phrases with the actual consequence.

Bad cleanup:

```text
That is the important boundary.
```

Better corpus prose:

```text
The Referee should keep these categories separate when deciding what a xenospecies can do in play.
```

Bad cleanup:

```text
Dead chemistry still matters.
```

Better corpus prose:

```text
Bio-organic residues may continue to affect later worlds after the original biosphere is dead. They are no longer alive, but they can still leave precursor molecules, isotopic traces, and chemical bias in the material from which later worlds form.
```

Bad cleanup:

```text
Human-legible alien Sophonts are a high-filter exception.
```

Better corpus prose:

```text
Only a small portion of alien Sophonts are familiar enough for Humans to understand quickly. Most remain strange in body, habit, environment, or social display. The familiar cases matter because they are the ones most likely to enter diplomacy, trade, rescue, migration, celebrity, crime, war, and Player Character contact.
```

### Analyst Voice Instead of Manuscript Voice

Do not leave the assistant's reasoning posture in the finished file. Phrases such as `the issue is`, `the clean synthesis is`, `the best version is`, `the stronger solution is`, `this solves the problem`, and `the stack becomes` belong to design discussion unless the document is explicitly a design note.

For a corpus file, write the result as settled setting explanation.

Bad cleanup:

```text
The clean synthesis is that Ash handles chemistry and Dream handles personhood.
```

Better corpus prose:

```text
Ash describes the chemical inheritance of a region. Dream describes the symbolic and Sophontic inheritance carried through Morfiuthelas. Together they explain why a few xenospecies are easier for Humans to understand than blind chance would suggest.
```

### Over-Compressed Boundary Labels

Do not overuse `boundary`, `gate`, `layer`, `filter`, `stack`, or `register` as substitute prose. Some of these may be correct technical terms in a specific document, but they should not appear as repeated signposts in every paragraph. When one of these terms is needed, define it once and then return to concrete explanation.

Prefer `category`, `question`, `case`, `condition`, `limit`, or the actual named setting term when those fit better. Prefer a sentence that tells the Referee what to decide.

### Importing Generic RPG Theory

Avoid `fiction-first`, `narrative economy`, `spotlight currency`, `player-facing loop`, `engagement model`, or similar terms unless the user explicitly asks for comparison to modern RPG theory.

### Writing Rules Like a White Paper

Avoid research-paper or white-paper phrasing in rules that players must use. Terms such as `register`, `pressure`, `vector`, `modality`, `operationalize`, `framework`, `payload`, `axis`, and `ontology` often make a rule sound more precise while making it harder to use.

Use ordinary game terms instead.

Prefer:

- `Add Weariness Level to the Target Number.`
- `Mark 1 Stress.`
- `Gain 1 Scar.`
- `Take DM -1 on the next roll.`
- `Recover HP equal to the listed value.`
- `Record the result on the character sheet.`

Do not replace simple instructions with technical phrasing unless the section is actually a technical lore section, a design note, or a developer-facing appendix.

### Erasing Hard Edges

Do not soften material about crime, slavery, corruption, war, exploitation, authoritarianism, or cruelty into neutral abstractions. SH44SER uses those hard edges to establish moral and legal texture.

## Final Checklist

Before considering a document ready, confirm:

- It uses the correct corpus register: SH44SER or DXD/Sarna Len.
- It does not weight the old style guide as prose canon.
- It states settled canon directly.
- It identifies the actor for rules and Referee guidance.
- It states triggers, costs, results, records, and limits where relevant.
- It preserves useful examples, formulas, lookup tables, and probability tables near where they are used.
- It preserves useful nested lists, ordered procedures, example blocks, and table-local notes when they are part of the rule.
- It keeps `For example` blocks near the rules they teach unless the target file is only a quick reference.
- Formulae have short lead-ins unless their terms were already established in the document header or immediately prior section.
- Player-facing rules use plain game words before technical or academic terms.
- It keeps named setting terms rather than generic abstractions.
- It removes transcript, prompt, and memo residue.
- It preserves consequence in lore and rules.
- It does not replace source prose with table rows when the source paragraph explains cause, consequence, institution, public meaning, or play use.
- User-provided source prose has been preserved as closely as possible, with only necessary corrections for spelling, grammar, punctuation, clarity, continuity, and corpus fit.
- No source paragraph has been paraphrased into a summary unless the original was unusable, obsolete, contradicted by later canon, duplicated by a stronger manuscript passage, or intentionally assigned to a quick-reference file.
- Narrative histories, nations, institutions, cultures, wars, disasters, and technologies use prose as the main reader path and tables as lookup support.
- Source appendices preserve provenance, but the primary home still carries the best source prose needed to teach the topic.
- DXD material identifies who rolls, whether the roll is public, and when hidden information is exceptional.
- Player-offered justifications and GM/Referee approval remain visible when the rule depends on them.
- It reads like it belongs inside the manuscript rather than inside a chat answer.
- It does not preserve UI-iteration shorthand such as `the important boundary`, `the key move`, `high-filter exception`, or `dead chemistry still matters` unless the document is explicitly a design note.
