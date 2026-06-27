# AGE Design Record — Objections and Resolutions

This design record captures the objection categories used by AGE as architectural pressure tests. Each objection is treated as a development constraint with a corresponding AGE mechanism.

## LMS-Graph Hard Problems

### HP-1 — Source Authority Resolution

Problem: authoritative sources can conflict.

Resolution: LMS-Graph stores source tier, version, scope, authority weight, conflict state, and human decision point. CAL presents weighted result sets rather than flattening conflict into a single unsourced answer.

### HP-2 — Training Cutoff Boundary

Problem: model weights are bounded by training time.

Resolution: LMS-Graph supplies maintained corpus state. The LLM interprets retrieved authority rather than relying on parametric recall.

### HP-3 — Semantic Disambiguation

Problem: the same word can mean different things in different domains.

Resolution: queries operate inside active partitions. Concern, role, spatial, narrative, and corpus partitions scope meaning before interpretation.

### HP-4 — Depth Traversal Control

Problem: recursive corpus traversal can pursue low-value paths.

Resolution: traversal uses breadth-first authority roots, priority weighting, utility scores, user-directed dive targets, and sub-optimal result tiers.

### HP-5 — Paywall and Access Rights

Problem: authoritative corpora may require licensed access.

Resolution: access rights are deployment configuration. The corpus envelope records available, inaccessible, and externally required authorities.

## LMS-Graph Engineering Problems

### EP-1 — Graph Coherence Under Parallel Write

Resolution: canonical IDs use URI, version, jurisdiction/scope, and source hash. Deduplication, AB-pruning, intent vectors, and conflict queues manage overlapping ingestion.

### EP-2 — Query Decomposition Audit Trail

Resolution: CAL records queried partitions, unqueried adjacent partitions, optimal paths, and sub-optimal dive targets.

### EP-3 — Negative Space Representation

Resolution: graph nodes can represent not-addressed, contested, jurisdiction-dependent, under-revision, prohibited, permitted, and unknown states.

### EP-4 — Response Confidence Stratification

Resolution: result envelopes carry authority tier, confidence tier, source scope, conflict flag, and human decision flag.

### EP-5 — Recursive Loop Detection

Resolution: traversal uses visited-state, versioned edge identity, mark-sweep, fast-follower detection, and subgraph hash checks.

### EP-6 — Monitor Agent Objective Function

Resolution: monitor utility combines coverage density, citation resolution rate, staleness index, conflict queue depth, unresolved authority count, and query failure patterns.

### EP-7 — Human Bandwidth at Scale

Resolution: low-stakes conflicts resolve by threshold; high-stakes or close-weight conflicts enter human review. Role Service allows specialist role delegation before final human decision.

### EP-8 — Graph Versioning

Resolution: LMS-Graph stores versioned snapshots and queryable historical states at configured intervals.

## Systemic Tensions

### ST-1 — Epistemic Over-Reliance

Resolution: AGE output envelopes make uncertainty, conflict, source scope, and human decision points visible.

### ST-2 — Corpus Capture

Resolution: certification artifacts and adversarial audit packs test corpus answers against dissenting, minority, superseded, and adjacent sources.

### ST-3 — Ossification Risk

Resolution: sub-optimal and wild-card result tiers preserve low-density novelty signals. Continuous ingestion updates the corpus graph.

### ST-4 — Jurisdiction and Scope

Resolution: jurisdiction/scope is a first-class partition key. Correctness is scoped before retrieval and interpretation.

### ST-5 — Liability and Deployment Posture

Resolution: professional consequence requires a human decision point. AGE supplies research, structured authority, audit logs, and decision support.

## AGE Architecture Objections

### AO-1 — LLM-as-State-Manager Inversion

Resolution: AGE externalizes state and uses the LLM as Fiction Constructor only.

### AO-2 — Bridge Layer Necessity

Resolution: the Bridge Layer is mandatory because it validates actions, enforces partition policy, routes modules, checks entity versions, and prevents direct state writes.

### AO-3 — State Summarization Failure

Resolution: State Assembler uses anchors, active invariant sets, scope filters, temporal compression, and priority rules. High-priority anchors remain active.

### AO-4 — Concurrent Write Conflicts

Resolution: OCC detects conflicts and routes them into game-mechanic resolution and conflict spotlights.

### AO-5 — Combat and Action Granularity

Resolution: granularity is presentation and orchestration. Domain modules receive atomic structured calls.

### AO-6 — NPC Agency Without Full Simulation

Resolution: NPC Goal Engine uses goal-flag loops, off-scene abstraction, and in-scene summarization. It avoids full BDI simulation at world scale.

### AO-7 — Campaign Depth vs Player Count

Resolution: AGE uses one-to-five-player troupes. Deep narrative play is optimized for smaller troupes; larger play shifts toward ensemble or tactical structures.

### AO-8 — Consistency at Scale

Resolution: AGE combines Single Source of Truth, narrative anchoring, hierarchical partitions, event propagation, output verification, and replay logs.

### AO-9 — Competitive Novelty

Resolution: AGE’s contribution is integration: constraint-first narrative runtime, state-authoritative modules, partitioned world scope, deterministic shareability, corpus arbitration, auditable roles, and semantic QA.
