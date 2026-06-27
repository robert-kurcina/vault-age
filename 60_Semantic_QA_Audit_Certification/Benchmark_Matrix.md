# Benchmark Matrix

## Runtime benchmarks

| Benchmark | Measures | Failure signal |
|---|---|---|
| State-prose consistency | Whether output matches committed state. | Prose invents, deletes, moves, reveals, or alters facts. |
| Replay determinism | Whether outcomes reproduce. | Same seed/action produces different structured outcome. |
| Scope transition correctness | Whether locale/world shifts preserve time and consequence. | Travel/downtime skips costs or events. |
| Hidden information control | Whether output leaks invisible facts. | Player sees engine-only or NPC-only knowledge. |

## CAL benchmarks

| Benchmark | Measures | Failure signal |
|---|---|---|
| Source grounding | Whether answer cites corpus evidence. | Answer relies on model memory. |
| Conflict detection | Whether competing authorities surface. | Conflict silently collapsed. |
| Version awareness | Whether correct corpus version applies. | Superseded or wrong version used. |
| Override learning | Whether human correction becomes test signal. | Same error repeats without trace. |

## Role benchmarks

| Benchmark | Measures | Failure signal |
|---|---|---|
| Contract adherence | Role stays within behavior and authority. | Role claims powers or knowledge it lacks. |
| Epistemic boundary | Role only uses permitted knowledge. | Hidden or out-of-scope knowledge leaks. |
| Evidence behavior | Role cites CAL or source when required. | Unsupported advice presented as authority. |

## Product benchmarks

| Benchmark | Measures | Failure signal |
|---|---|---|
| Play continuity | Whether rulings and validation preserve pacing. | Frequent stalls or clarifications. |
| Author usability | Whether authors can publish valid packages. | Schema burden blocks creation. |
| Human trust | Whether users understand why outcomes happened. | Outcomes feel arbitrary or opaque. |
