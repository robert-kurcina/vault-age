# AGE Subsystem Index

## Reading rule

The subsystem order is the implementation order. Later layers depend on earlier layers. Agent Service and professional-domain extensions are downstream and should not influence the first MVP beyond keeping interfaces clean.

| Subsystem | Directory | Primary question answered |
|---|---|---|
| Executive and Ontology | `00_Executive_and_Ontology/` | What is AGE, what words mean, what is in scope, and what is the product claim? |
| Engineering Handoff | `05_Engineering_Handoff/` | What gets built first, through which contracts, and how is success tested? |
| Core Runtime and Bridge | `10_Core_Runtime_and_Bridge/` | How does AGE prevent language from owning state? |
| Engine Execution Spine | `15_Engine_Execution_Spine/` | What is the exact input-to-output runtime flow? |
| Narrative Scope and AGEScript | `20_Narrative_Scope_and_AGEScript/` | How does authored narrative remain flexible without losing consequence? |
| Spatial, Narrative, Temporal Scope | `25_Spatial_Narrative_Temporal_Scope/` | How does AGE move from locale to world scale and advance time? |
| Partitions, State, Memory | `30_Partitions_State_Memory/` | How are state, memory, knowledge, and scope bounded? |
| World Generation, Lazy Ontology, Overlays | `35_World_Generation_Lazy_Ontology_Overlays/` | How does the world become detailed without simulating everything? |
| LMS-Graph and CAL | `40_LMS_Graph_Corpus_Arbitration/` | How does AGE answer unstructured rules/corpus questions from sources? |
| AGEScript, Plot, Eventing | `45_AGEScript_Plot_Eventing/` | How do events, tables, and plot rebinding operate? |
| Role Service | `50_Role_Service_and_Actors/` | How are NPCs, advisors, and bounded roles defined and audited? |
| Authoring UX | `55_Authoring_UX_Capture/` | How do authors create usable content without programming every branch? |
| Semantic QA, Audit, Certification Artifacts | `60_Semantic_QA_Audit_Certification/` | How are drift, contradiction, replay, and role/corpus quality tested? |
| Client, Multiplayer, Output | `70_Client_Multiplayer_Output/` | How do players interact, communicate, and receive verified output? |
| Agent Service Extensions | `80_Agent_Service_Extensions/` | How would qualified roles later act through external APIs? |
| Product Roadmap, Business Risk | `90_Product_Roadmap_Business_Risk/` | What is the viable wedge, risk model, and expansion path? |
| Source Material | `95_Source_Material_Reorganized/`, `99_Original_Inputs/` | What source material informed the archive? |
