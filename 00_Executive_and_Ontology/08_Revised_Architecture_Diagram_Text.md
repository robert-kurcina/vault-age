# Amazing Game Engine [AGE] Architecture Diagram — Text Form

## Local definitions

Amazing Game Engine [AGE] means the complete platform described by this archive.

AGE Engine means the deterministic runtime inside AGE.

Large Language Model [LLM] means a generative language model used for language interpretation or presentation.

Large Model System [LMS] means the wider model, retrieval, graph, tool, agent, and workspace system around one or more LLMs.

Large Model System Graph [LMS-Graph] means the maintained graph/relational corpus substrate.

Corpus Arbitration Layer [CAL] means the component that answers unstructured questions against LMS-Graph.

Non-player character [NPC] means a character controlled by the system, Referee, or authored scenario rather than by a player.

```text
USER / PLAYER / AUTHOR
        |
        v
INPUT COORDINATOR
- classify input
- detect intent
- separate IC, OOC, rules query, author command, system command
- build Action Candidate or CAL Query
        |
        +------------------------------+
        |                              |
        v                              v
BRIDGE LAYER                      CAL QUERY GATE
- validate action                 - validate corpus question
- check permissions               - identify active corpus
- check scope/timing              - identify table/system context
- check partition access          - route to LMS-Graph partitions
- check role constraints                    |
        |                                    v
        v                              CORPUS ARBITRATION LAYER [CAL]
DOMAIN MODULES                     - decompose query
- spatial graph                    - retrieve corpus nodes
- combat/rules runtime             - weigh authority
- inventory                        - surface conflicts
- communication                    - produce answer envelope
- NPC goals                        - log arbitration
- event generator                           |
- living world                              v
- overlays                         RULES SERVICE / GUIDANCE SERVICE
        |                           - quick ruling for play
        v                           - detailed ruling for audit
STATE MUTATION ENGINE                      |
- commit validated deltas                  v
- version state                    HUMAN AUTHORITY POINT
- write audit trail                - referee / table / author / reviewer
        |                           - professional authority later
        v
EVENT BUS
- propagate consequences
- schedule ticks
- route ripples across partitions
        |
        v
STATE ASSEMBLER
- select active facts
- include narrative anchors
- include role constraints
- include CAL result if relevant
- bound context packet
        |
        v
FICTION CONSTRUCTOR [LLM]
- render prose
- preserve semantic content
- obey state and output constraints
- no state ownership
        |
        v
OUTPUT VERIFIER
- check against committed state
- check rules and CAL result
- check role constraints
- reject or repair contradictions
        |
        v
CLIENT OUTPUT + REPLAY LOG
- player presentation
- original/processed communication
- sync state
- seed/action/state/ruling log
```

## Core separation

AGE Engine owns state.

LMS-Graph owns corpus structure.

CAL arbitrates corpus questions.

Role Service owns role behavior.

Agent Service, later, owns bounded external action.

The Fiction Constructor renders. It does not own any of those authority layers.
