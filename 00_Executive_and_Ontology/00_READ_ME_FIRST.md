# Read Me First — AGE Development Orientation

AGE should be read as a platform architecture, not as a single game feature. The first product is a game-native runtime because games provide the safest and richest proving ground for persistent state, rules arbitration, authorship tooling, role behavior, natural-language interaction, and replayable audit trails.

The central engineering rule is simple:

```text
The engine owns truth. The LLM renders truth.
```

The LLM may help classify input, phrase choices, summarize state, and produce prose, but it does not decide canonical outcomes, write state, advance time, arbitrate rules, invent hidden facts, or override human authority.

The central corpus rule is equally simple:

```text
The corpus answers from sources. The LLM explains the sourced answer.
```

LMS-Graph stores the bounded corpus. CAL arbitrates queries against that corpus. Rules Service is the first CAL deployment. Role Service is separate and governs bounded actor behavior.

## Non-negotiable vocabulary

- AGE: the total platform.
- AGE Engine: the deterministic runtime.
- Fiction Constructor: the LLM presentation layer.
- LMS: the larger model/tool/agent system, not merely an LLM.
- LMS-Graph: the maintained graph/relational corpus substrate.
- CAL: Corpus Arbitration Layer, the query-and-ruling component.
- Rules Service: rules-specific CAL deployment.
- Role Service: bounded role behavior.
- Agent Service: later MCP/API-connected action layer.
- RaaS: deprecated as an umbrella term.

## First build target

The first build target is not professional law, medicine, building code, or unrestricted enterprise knowledge. The first build target is a single-troupe AGE Engine with a bounded game rules corpus. This test bed is high-volume, low-stakes, versioned, conflict-rich, and structurally similar to regulated corpora without the same liability exposure.
