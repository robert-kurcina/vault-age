# Claims and Implementation — Partitions, State, and Memory

## Claims

- State is partitioned by authority and scope.
- Prose logs are not canonical state.
- State Assembler provides bounded context without giving away the world.

## Implementation steps

1. Define AbstractPartition interface.
2. Define DomainPartition manifests.
3. Implement entity/flag/narrative-anchor records.
4. Build scoped summaries.
5. Implement access rules.
6. Integrate State Assembler with Output Verifier.

## Risks and controls

- Risk: partition leakage. Control: access rules.
- Risk: over-partitioning. Control: start with few partition types.
- Risk: summary loss. Control: narrative anchors and verifier.
