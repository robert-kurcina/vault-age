# Reader Guide for the Amazing Game Engine [AGE] White Papers

## Local definitions

Amazing Game Engine [AGE] means the complete platform described by this archive.

AGE Engine means the deterministic runtime inside AGE.

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Quality Assurance [QA] means testing and review; Semantic QA tests meaning, authority, role behavior, rules, state, and prose-state agreement.

## Reading order

Read the executive brief first. Then read the ontology primer. Then read the subsystem index. After that, read the white papers in subsystem order.

## What the white papers are

The white papers are development-facing architecture briefs. They explain the subsystem, the problem it addresses, the operating model, rewards, risks, mitigation strategy, implementation path, and success criteria.

## What they are not

They are not marketing copy. They are not legal claims. They are not promises that AGE solves correctness, hallucination, or professional liability. They define how AGE should be built and what each subsystem must prove.

## Core doctrine to preserve

AGE Engine owns state.

LMS-Graph owns corpus structure.

CAL arbitrates corpus questions.

Rules Service is a CAL deployment.

Role Service governs role behavior.

Agent Service governs later external action.

The Fiction Constructor renders.

Human authority remains final where judgment is required.

## Using the white papers for implementation

For each subsystem, convert the white paper into schemas, APIs, validation rules, test fixtures, QA rubrics, and implementation milestones. The corresponding `Claims_and_Implementation.md` file provides the first work breakdown.
