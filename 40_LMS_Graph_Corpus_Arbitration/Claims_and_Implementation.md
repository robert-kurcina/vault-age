# Large Model System Graph [LMS-Graph] and Corpus Arbitration Layer [CAL] — Claims and Implementation

## Local definitions

Large Language Model [LLM] means a generative language model used for language interpretation or presentation.

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Minimum Viable Product [MVP] means the smallest product that proves the core AGE loop.

## Claims

LMS-Graph can store a bounded corpus in source-bound, versioned, authority-tiered graph/relational form.

CAL can answer unstructured questions by retrieving from LMS-Graph rather than relying on LLM memory.

Rules Service can use CAL to arbitrate game rules questions during play.

A game rules corpus is the correct first test bed because it is bounded, high-volume, low-stakes, versioned, and conflict-rich.

## Implementation work

Define corpus node schema.

Define source and authority tier schema.

Define edge types: cites, overrides, supplements, conflicts, defines, excepts, depends-on, applies-to, supersedes, table-overrides.

Define relational fields: version, edition, source owner, source type, effective date, rule parameter, table scope, license state.

Build ingestion from owned/licensed game rules.

Build query decomposition and partition selection.

Build retrieval, ranking, conflict detection, and confidence weighting.

Build quick ruling and detailed ruling output.

Build referee override capture.

Build arbitration replay logs.

Build monitor metrics.

## Risks

Licensing, latency, mistaken authority tiering, query misrouting, over-trust, graph drift, and incomplete coverage.

## Mitigation

Start with controlled corpus. Use quick/deep modes. Keep the answer envelope visible. Record human overrides. Treat unsupported material explicitly. Preserve versioned snapshots.

## MVP success

A player asks a rules question during play. Rules Service identifies the relevant corpus partition, returns a quick ruling with authority tier and table scope, allows the referee to accept or override, records the decision, and makes the ruling reviewable.
