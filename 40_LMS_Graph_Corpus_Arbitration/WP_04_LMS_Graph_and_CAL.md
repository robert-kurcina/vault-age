# White Paper 04 - Large Model System Graph and Corpus Arbitration Layer

## Purpose

The Amazing Game Engine [AGE] uses the Large Model System Graph [LMS-Graph] to ground answers in maintained source material. A large model system [LMS] is the broader arrangement around one or more language models, including retrieval, graph search, tools, workspaces, agents, and task routing. LMS-Graph is the graph and relational knowledge substrate built from authoritative or configured source roots. The Corpus Arbitration Layer [CAL] is the service that answers unstructured questions against LMS-Graph.

This white paper explains how AGE replaces unanchored model recall with source-grounded arbitration.

## Why LMS-Graph Exists

A large language model [LLM] stores patterns in model weights. That makes it useful for language, synthesis, and explanation. It does not make it a reliable authority for current rules, law, procedure, standards, errata, licensing requirements, or table policy. The same sentence may be correct in one jurisdiction, obsolete in another, contradicted by errata, or true only under a specific edition.

LMS-Graph exists so AGE can route questions to maintained sources instead of depending on parametric memory. It does not promise automatic correctness. It promises traceability, boundedness, version awareness, conflict disclosure, and human decision points.

## Graph and Relational Structure

LMS-Graph uses graph structure where relationships matter. It stores citations, dependencies, exceptions, supersession chains, rule references, authority tiers, jurisdiction, conceptual adjacency, and conflicts. It uses relational structure where fields matter. It stores dates, thresholds, table entries, values, version numbers, requirements, statuses, identifiers, and classifications.

A game rule corpus benefits from both structures. A rule may cite another rule, depend on a condition, be superseded by errata, have an example, and be altered by table policy. It may also contain fixed numbers, target values, costs, ranges, durations, and version fields. Professional corpora have the same pattern at higher consequence.

## Corpus Ingestion

Corpus ingestion should begin from authoritative roots. In a game corpus, roots are rulebooks, errata, official examples, supplements, author rulings, and table policy. In a professional corpus, roots may include statutes, regulations, standards, official guidance, code books, case law, agency interpretations, licensing boards, or institutional procedures.

The ingestion process should proceed breadth-first before depth-first. Breadth-first ingestion builds baseline context and authority structure. Depth-first ingestion follows specific citations, definitions, exceptions, and cross-references. Agentic retrieval can divide work, but parallel ingestion must deduplicate sources, reconcile identifiers, and preserve provenance.

Provenance means the record of where a claim came from, which version it belongs to, and how it entered the corpus. A source without provenance may be useful for discovery. It should not become authority.

## Arbitration Envelope

CAL returns an arbitration envelope. The envelope should contain the user question, interpreted question, active corpus partition, applicable version, answer, source basis, authority weight, confidence, conflicts, missing coverage, human decision point, and suggested ruling if the domain permits suggestions.

![Figure: Corpus Arbitration Layer](../assets/diagrams/cal_arbitration.png)

```mermaid
flowchart LR
    Query[Unstructured question] --> Interpret[Query interpretation]
    Interpret --> Partitions[Corpus partitions]
    Partitions --> Sources[Source retrieval]
    Sources --> Weigh[Authority and version weighing]
    Weigh --> Conflicts[Conflict disclosure]
    Conflicts --> Human[Human decision point]
    Human --> Envelope[Arbitration Envelope]
```

For a game, the envelope may say that the core rule supports one answer, an expansion creates an exception, and the table policy must decide whether the expansion is active. For a professional domain, the envelope may say that the national rule is modified by local jurisdiction, that the source is paywalled or missing, or that a licensed professional must decide.

## Human Decision Points

Conflicting authority is normal. Courts disagree. Agencies revise guidance. Local amendments modify model codes. Game errata modifies books. Supplements create optional rules. Referees create house policy. CAL should not hide conflict in a single confident paragraph. It should expose the conflict and identify the human decision point.

This is one of AGE's central safeguards. The system can assemble and weigh evidence. It should not pretend that weighing evidence always produces an automatic final answer.

## Rules Service as First Deployment

The Rules Service is the first CAL deployment. It applies CAL to a bounded game rules corpus. This is the correct first target because game rules contain ambiguity, exceptions, examples, table policy, and human judgment while remaining lower consequence than law, medicine, construction, finance, or safety-critical engineering.

The Rules Service should answer quick rulings during play and detailed rulings outside play. A quick ruling gives the Referee a concise answer, active source basis, and decision point. A detailed ruling gives the full arbitration envelope, conflict analysis, examples, and test cases.

## Example

A player asks, "Can I use this movement power while carrying an unconscious ally through a locked window?" CAL should not answer from general model memory. It should retrieve the movement power, carrying rules, action economy, object interaction rules, window obstruction rules, unconscious ally state, and any table policy about forced movement or carried characters. If the rules conflict, it should expose the conflict. If the rules do not cover the case, it should identify the Referee decision point and offer a bounded ruling path.

## Risks

The risk is overclaiming. LMS-Graph may have incomplete coverage, stale sources, missing paywalled material, weak jurisdiction modeling, or unresolved contradictions. CAL must say when coverage is incomplete. Another risk is graph sprawl. Recursive ingestion can consume resources without improving answer quality. The ingestion system therefore needs priority rules, stopping criteria, freshness checks, and review queues.

## Authority Tiers

Authority tiers state which sources control when sources disagree. A core rulebook may outrank a blog post. Errata may outrank the first printing. A table policy may override an optional rule for one troupe. A local jurisdiction may override a model code. A later statute may supersede an earlier agency guide. CAL should not flatten these tiers.

Each corpus must define its own authority model. A game corpus and a legal corpus do not use the same authority rules. The important thing is not one universal hierarchy. The important thing is that the active hierarchy is explicit and inspectable.

## Coverage Maps

A coverage map states what the corpus contains and what it does not contain. This is necessary for trust. If a professional corpus lacks paywalled standards, local amendments, or recent decisions, CAL must expose the gap. If a game corpus lacks a supplement, the Rules Service should not act as if the supplement was considered.

Coverage maps also guide ingestion priorities. The system should improve the corpus where missing coverage actually affects user questions.

## Quick Rulings and Detailed Rulings

CAL should support quick rulings and detailed rulings. A quick ruling is used during play. It gives the likely answer, controlling source, active exception, and Referee decision point in compact form. A detailed ruling is used for review, publication, or dispute. It gives the full source chain, conflict analysis, alternatives, and test cases.

The two modes should use the same corpus. They differ in presentation and latency, not authority.

## Success Criteria

This subsystem succeeds when an unstructured question produces a source-grounded answer whose authority, version, conflict status, and human decision point are visible. It fails if it merely produces a confident answer that cannot be traced.
