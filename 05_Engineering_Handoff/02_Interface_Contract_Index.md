# Interface Contract Index

## Local definitions

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Relational Database Management System [RDBMS] means a relational database system.

Uniform Resource Identifier [URI] means a string that identifies a resource.

## Purpose

This file names the contracts that must be specified before implementation can remain coherent. Contract names should remain stable even if schemas evolve.

## Runtime contracts

### UserInput
Raw user entry with identity, session, timestamp, input mode, visibility, and channel.

### ActionCandidate
Structured interpretation of UserInput. Includes actor, intent, targets, proposed action type, confidence, required modules, and ambiguity flags.

### ValidationResult
Bridge Layer result. Includes allowed/denied/needs-human/needs-CAL/needs-clarification, reasons, required state versions, and scope.

### ModuleResolution
Domain Module outcome. Includes deterministic resolver, seed, success/failure, costs, effects, and proposed state deltas.

### StateDelta
Canonical mutation request. Includes entity IDs, prior versions, new values, provenance, authority, and rollback data.

### EventPacket
Published consequence. Includes event type, scope, visibility, affected partitions, timing, and subscribers.

### ContextPacket
State Assembler output for Fiction Constructor. Includes committed facts, narrative anchors, local state, relevant history, role constraints, and output boundaries.

### FictionOutput
Generated presentation. Includes prose, choices, summaries, dialogue, and visible ruling text.

### VerificationResult
Output Verifier judgment. Includes pass/fail, contradiction flags, unauthorized facts, invalid reveals, invalid rulings, and repair instructions.

### ReplayEntry
Audit unit. Includes seed, action sequence, entity versions, validations, resolutions, state deltas, events, fiction output, verifier result, and human overrides.

## CAL contracts

### CorpusSource
A source unit with URI/path, version, authority tier, scope, license, effective date, and provenance.

### CorpusNode
Graph/RDBMS representation of a rule, concept, citation, exception, example, table fact, or interpretation.

### ArbitrationQuery
Interpreted user question with corpus partition, scope, terms, ambiguity flags, and desired depth.

### RetrievedEvidence
Source-bound evidence returned by LMS-Graph.

### ArbitrationEnvelope
CAL answer with question, interpretation, sources, authority tier, version, confidence, conflicts, answer, alternatives, human decision point, and deep-dive paths.

### OverrideRecord
Human acceptance, modification, or rejection of a ruling.

## Role contracts

### RoleSemanticContract
Role definition including purpose, knowledge scope, permissions, evidence rules, behavior constraints, prohibited claims, memory scope, and audit requirements.

### RoleResponseEnvelope
Role output with contract version, evidence used, memory scope, behavior checks, CAL references, and drift flags.
