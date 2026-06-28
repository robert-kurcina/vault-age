# AGE Style Guide

**Purpose:** Define the prose, technical-presentation, source-retention, diagram, PDF, and archive rules for Amazing Game Engine [AGE] documents.

**Audience:** authors, engineers, editors, model assistants, implementation leads, and reviewers preparing AGE technical papers, specifications, runtime examples, and PDF exports.

**Canonical Authority:** This file controls AGE document presentation. It inherits useful rails from the SH44SER / DXD style guide where those rails fit AGE. It does not import SH44SER setting voice, game terminology, or Referee language into AGE unless a document is explicitly comparing AGE to SH44SER.

## 1. Core AGE Document Voice

AGE documents are technical design documents for a state-authoritative narrative engine. They should read like system papers, implementation specifications, and source-promoted architecture references. They should not read like marketing copy, short outlines, pitch decks, or generic consultant summaries.

AGE prose should usually move in this order:

1. name the subsystem;
2. define any term or acronym before using it;
3. state the problem the subsystem solves;
4. describe the target environment;
5. define the abstraction;
6. show the data model, property sheets, packets, tables, or service contracts;
7. explain normal execution;
8. explain failure behavior;
9. show acceptance tests, replay checks, or evaluation criteria;
10. state what must be recorded, versioned, committed, or audited.

A useful AGE document teaches the reader how the system works. A weak AGE document merely names components.

## 2. Definition-Before-Use Rule

No acronym, named subsystem, property-sheet family, runtime packet, service name, or specialized concept may be used before it is defined in the same reader path.

Preferred form:

```text
The Amazing Game Engine [AGE] is a state-authoritative narrative engine. AGE uses generated prose, but generated prose is not itself authoritative.
```

Use the bracketed abbreviation once. After that, the abbreviation may be used.

This rule applies to headings when practical. A file title may use AGE if the file name requires it, but the first body paragraph must expand it.

Common AGE definitions include:

- Amazing Game Engine [AGE];
- large language model [LLM];
- Large Model System [LMS];
- Large Model System Graph [LMS-Graph];
- Corpus Arbitration Layer [CAL];
- DomainPartition;
- AbstractPartition;
- property sheet;
- Actor Sheet;
- Location Sheet;
- Object Sheet;
- Event Sheet;
- Role Sheet;
- AGEScript;
- JavaScript Object Notation [JSON];
- YAML Ain't Markup Language [YAML];
- Structured Query Language [SQL];
- Optimistic Concurrency Control [OCC];
- Retrieval-Augmented Generation [RAG];
- Application Programming Interface [API];
- Quality Assurance [QA];
- Minimum Viable Product [MVP].

## 3. Lists, Indentation, and Procedure Shape

AGE documents should use indentation, ordered lists, unordered lists, and nested lists whenever those structures make process visible.

Use ordered lists for:

1. runtime execution steps;
2. algorithms;
3. transaction sequences;
4. conflict-resolution procedures;
5. source-promotion workflow;
6. PDF export workflow;
7. acceptance-test procedure;
8. implementation order.

Use unordered lists for:

- design requirements;
- invariants;
- failure cases;
- role permissions;
- property-sheet fields;
- packet components;
- examples that do not require sequence;
- checklist items.

Use nested lists when a rule or procedure has pass, fail, record, or exception branches.

Preferred AGE procedure form:

```text
The State Mutation Engine commits an approved mutation.

1. Read every source sheet at its declared version.
2. Check partition authority.
3. Check invariants.
4. Apply the mutation.
5. Increment affected versions.
6. Append the event log record.
7. Return a committed state envelope.

On version conflict:

- retry if the conflict policy allows automatic retry;
- call a game-resolution procedure if the conflict is a simultaneous player action;
- reject the mutation if neither retry nor resolution is valid.
```

Do not flatten this into a single paragraph when the reader needs the order.

## 4. Demonstrate the System

AGE documents should demonstrate process, algorithms, property sheets, calculations, technical data, and state transitions whenever the source material supports them.

A subsystem paper should include at least one of the following:

- a property sheet;
- a request packet;
- a response packet;
- a mutation packet;
- an event record;
- a database schema;
- a pseudocode algorithm;
- a calculation table;
- a replay trace;
- an acceptance-test manifest;
- a failure-mode table.

A white paper that says AGE has time is not sufficient. It should show a TickPolicy, a transition packet, an event due at a tick, and the consequence of crossing that tick.

A white paper that says AGE has object state is not sufficient. It should show an Object Sheet, ownership or container fields, version fields, and mutation rules.

## 5. Diagrams and Illustrations

Use diagrams or illustrations whenever architecture, execution, data flow, state relations, partition topology, or causal movement would otherwise require dense prose.

Acceptable diagram sources include:

- Graphviz DOT;
- MermaidJS when the export pipeline supports it reliably;
- rendered PNG or SVG assets;
- simple tables when graphical layout would add little value.

Every diagram should have:

1. a short lead-in paragraph;
2. a caption or alt text in the Markdown when practical;
3. source retained in `assets/diagrams/`;
4. rendered output retained in `assets/diagrams/`;
5. a surrounding explanation that makes the document useful even if the diagram is unavailable.

Do not let a diagram replace the explanation. The prose should teach the reader; the diagram should compress the relationship.

## 6. Property Sheets, Packets, and Technical Examples

AGE state is not prose memory. It is a structured state model. AGE documents should therefore show state records directly.

Use fenced code blocks for:

```yaml
sheet_family: ObjectSheet
object_id: obj_iron_key
object_type: key
current_holder_container: inv_npc_bartender_orren
version: 7
```

Use tables for fixed comparisons:

| Record | Owns | Required invariant |
| --- | --- | --- |
| Actor Sheet | agents and identity | each actor has exactly one active location |
| Object Sheet | items and resources | each object has one holder, container, or location |
| Event Sheet | scheduled or triggered events | each event has a due tick or trigger |

Use pseudocode only when algorithmic control matters:

```text
function commitMutation(mutation):
  read required source versions
  reject if any version changed
  reject if partition authority is missing
  apply mutation
  append event log record
  return committed state envelope
```

## 7. Calculations and Evaluation

When a document includes cost, time, probability, scale, latency, storage, drift, branch growth, or replay scoring, show the calculation.

Example:

```text
Naive branch count = choices_per_player ^ player_count.
For 5 players with 3 choices each, naive branch count = 3 ^ 5 = 243.
AGEScript should collapse those choices through aggregation rules before rendering the outcome.
```

Every calculation needs:

1. the variables defined before use;
2. the formula;
3. an example;
4. the consequence for implementation.

## 8. Source Promotion and Resource Retention

The origin branch is source material. It must remain available inside the archive under `_resource/`.

Required layout:

```text
_resource/
  origin_branch/
    Archive.zip
    extracted/
  style_guides/
    00_AGE_STYLE_GUIDE.md
    00_SH44SER_STYLE_GUIDE.md
  comparison_whitepapers/
    <reference PDFs supplied by the user>
  resource_inventory/
    00_Resource_Inventory.md
```

Do not exile important source meaning into `_resource/` only. The primary documents must promote the useful concepts into reader-facing prose, diagrams, examples, and specifications.

Keep the resource directory because it allows audit, comparison, and recovery of source intent.

## 9. Archive Packaging

A delivered AGE archive must include generated PDFs inside the archive, not only as separate downloadable files.

Required layout:

```text
90_PDF_Exports/
  AGE_Technical_Executive_Summary_*.pdf
  AGE_Aggregated_Technical_White_Papers_*.pdf
```

The archive may also provide standalone copies for convenience, but the archive itself must be complete.


## 10. Retrieval, Context Budget, and Partition Authority

Retrieval-Augmented Generation [RAG] is a method that retrieves source material and places it into a model context. In AGE, RAG is not a partition architecture, not a truth store, not a mutation mechanism, and not an efficient substitute for structured state.

Use this doctrine:

1. Prefer structured state reads when the answer can be found in property sheets, event logs, partition records, source graphs, or projection tables.
2. Use retrieval only when the structured state or source graph requires source-text support, conflict evidence, flavor recovery, or authorial citation.
3. Scope retrieval by partition, source authority, time validity, role permission, and context budget.
4. Treat retrieved text as read-only evidence until the Corpus Arbitration Layer [CAL] or State Mutation Engine accepts it through normal authority rules.
5. Record every retrieval request that materially affects a response, including source set, retrieval snapshot, token budget, and reason for use.

Retrieval consumes input context. It can crowd out more important state packets, event records, rules, and visibility constraints. AGE documents should therefore avoid making RAG appear coequal with partitions. The correct relationship is:

```text
structured state first;
partition scope second;
corpus arbitration when needed;
retrieval only as a budgeted support tool;
state mutation only through commit authority.
```

## 19. PDF Export Rules

PDF exports must be generated from the Markdown source in the archive and then verified by rendering sample pages to images.

PDF requirements:

1. include a table of contents;
2. do not force page breaks before major top-level sections;
3. set ordinary body prose in two columns;
4. keep tables, diagrams, illustrations, and code blocks full-width;
5. preserve diagrams and tables;
4. avoid clipped text, broken tables, black squares, and missing glyphs;
5. include an Addendum section;
6. place glossary and citations in the Addendum;
7. keep generated PDFs in `90_PDF_Exports/` inside the archive.

For Pandoc and LaTeX exports, do not enforce automatic page breaks before top-level Markdown headings unless a special print edition explicitly requires that treatment.

```css
.top-section { break-before: auto; }
```

Do not insert manual page-break clutter into Markdown files. Use ordinary heading flow unless a special print edition calls for explicit page starts.

## 19. Tables and Post-Table Notes

Tables are useful when the reader compares structured data. Tables should not become the only place where a concept is explained.

Use prose first when the table describes:

- architecture;
- state ownership;
- time behavior;
- partition boundaries;
- source authority;
- rule consequences;
- failure behavior;
- implementation decisions.

After a table that uses local shorthand, define that shorthand near the table.

```text
Notes:

- `OCC` means Optimistic Concurrency Control.
- `tick` means the active integer time unit owned by the World Time Authority.
- `version` means the sheet version read or written during a transaction.
```

## 19. Algorithms and Runtime Procedure

When AGE behavior is algorithmic, state it as an algorithm. Do not describe deterministic runtime behavior as a vague design goal.

A good algorithm section names:

1. actor or service;
2. input packet;
3. source reads;
4. validation steps;
5. mutation steps;
6. output packet;
7. failure branches;
8. audit records.

Example headings:

- Runtime Turn Procedure;
- Location Transition Procedure;
- Event Due-Tick Procedure;
- Object Transfer Procedure;
- CAL Answer Procedure;
- Replay Certification Procedure.

## 19. Terminology and Capitalization

Preserve AGE term capitalization when a word has become a named system term.

Use:

- Amazing Game Engine [AGE];
- DomainPartition;
- AbstractPartition;
- ConcernPartition;
- SpatialPartition;
- TickPolicy;
- BridgePolicy;
- Actor Sheet;
- Location Sheet;
- Object Sheet;
- Event Sheet;
- Role Sheet;
- State Mutation Engine;
- Fiction Constructor;
- Consistency Arbiter;
- Corpus Arbitration Layer [CAL];
- Large Model System Graph [LMS-Graph];
- AGEScript.

Do not invent new capitalization to make generic words look technical. If a term is not a named AGE component, keep it ordinary.

## 19. Avoid Analyst Voice

Do not leave assistant reasoning posture in finished AGE documents.

Avoid:

- "the clean version is";
- "the key move is";
- "this solves the problem";
- "the stack becomes";
- "the important boundary is";
- "this is more robust" without showing why.

Replace these with direct system explanation.

Weak:

```text
The key move is that the LLM does not own truth.
```

Better:

```text
The large language model [LLM] may propose prose and candidate deltas, but only the State Mutation Engine commits canonical state.
```

## 19. Human and System Authority

AGE documents should distinguish human authority, runtime authority, and model output.

- The author creates source material and system rules.
- The Referee or game operator may make campaign rulings where the product includes that role.
- The runtime commits state.
- The Corpus Arbitration Layer weighs sources.
- The LLM renders, classifies, or proposes.
- The Output Verifier rejects unfaithful output.

Do not imply that an LLM can silently create canon, silently alter inventory, silently resolve rules conflicts, or silently move time.

## 19. Unsettled Material

If a value remains unsettled, say so directly. Do not write unsettled ideas as settled implementation.

Use:

```text
This remains under evaluation.
The current preferred treatment is...
The first implementation should...
The archive does not yet contain enough detail to specify...
```

Do not use vague language for settled material.

## 19. Addendum Requirement

Major AGE PDFs must end with an Addendum section. The Addendum should contain:

1. glossary;
2. citations or reference papers when relevant;
3. source-retention note;
4. artifact inventory when useful;
5. any unresolved technical cautions that do not belong in the main reader path.

The Addendum should not become the primary home for important architecture. The main document still must teach the architecture.

## 19. Final Checklist

Before an AGE document is ready, confirm:

- Terms and acronyms are defined before use.
- The document uses ordered lists where process order matters.
- The document uses unordered lists for parallel requirements, invariants, and examples.
- Major procedures show actor, trigger, input, output, record, and failure behavior.
- Property sheets or packet examples are present where the subject is stateful.
- Calculations are shown when scale, time, branch growth, cost, probability, or replay metrics matter.
- Diagrams are present where architecture or flow would otherwise be dense.
- Diagrams have source and rendered output in `assets/diagrams/`.
- PDF exports include a table of contents.
- PDF exports do not force page breaks before top-level sections.
- Major PDFs have an Addendum with glossary and citations.
- Generated PDFs are included inside `90_PDF_Exports/`.
- Origin source remains in `_resource/origin_branch/`.
- Comparison papers and style guides remain in `_resource/` when supplied.
- The document reads like an implementable technical reference rather than an outline.

# Addendum

## Glossary

**AbstractPartition:** The conceptual partition contract from which concrete AGE partition families derive.

**Amazing Game Engine [AGE]:** A state-authoritative narrative engine that renders prose from committed structured state.

**AGEScript:** AGE's authoring and runtime scene language for spotlights, choices, aggregation, outcomes, state mutations, and narrative hooks.

**Application Programming Interface [API]:** A service contract that defines request packets, response packets, and allowed operations.

**Corpus Arbitration Layer [CAL]:** The service that weighs source authority, resolves or exposes source conflict, and returns auditable rule or lore answers.

**DomainPartition:** A runtime partition that owns bounded state, time policy, bridge policy, and mutation authority.

**JavaScript Object Notation [JSON]:** A machine-readable structured data format used by AGE examples and compiled runtime artifacts.

**Large Language Model [LLM]:** A statistical text model used by AGE for rendering, classification, and candidate generation, but not as final state authority.

**Large Model System [LMS]:** The full model-support system around an LLM, including retrieval, tools, graph search, routing, memory, and audit.

**Large Model System Graph [LMS-Graph]:** The AGE graph of sources, claims, concepts, versions, dependencies, and conflicts.

**Minimum Viable Product [MVP]:** The smallest implementation that proves AGE's state authority, partitioning, time, location, AGEScript, corpus arbitration, replay, and QA.

**Optimistic Concurrency Control [OCC]:** Version-checking method that prevents silent overwrite when concurrent clients mutate the same state.

**Property Sheet:** A structured state record for an entity, object, location, event, partition, or role.

**Quality Assurance [QA]:** The testing and certification practice used to verify state, rules, replay, source authority, and output fidelity.

**Retrieval-Augmented Generation [RAG]:** A method that retrieves source material for model context. In AGE, Retrieval-Augmented Generation can support state assembly and corpus arbitration, but it consumes model context and does not replace partition authority.

**Structured Query Language [SQL]:** The relational database language used in AGE schema sketches.

**TickPolicy:** A partition's rule for mapping narrative scale to time units.

**YAML Ain't Markup Language [YAML]:** A human-readable data format used for AGE examples and authoring sketches.

## Citations and Reference Sources

- SH44SER / DXD Style Guide, supplied by the user and retained as `_resource/style_guides/00_SH44SER_STYLE_GUIDE.md`.
- AGE origin branch archive, retained as `_resource/origin_branch/Archive.zip` and `_resource/origin_branch/extracted/`.
- Comparison systems papers supplied by the user and retained in `_resource/comparison_whitepapers/`.
- Generated AGE technical documents retained as Markdown sources and PDF exports inside this archive.
