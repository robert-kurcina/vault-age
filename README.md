# AGE Technical Presentation Pass 6 Single Column Archive

This archive applies the AGE Style Guide to the technical white-paper corpus and corrects the prior over-promotion of Retrieval-Augmented Generation [RAG]. In this pass, RAG is treated as a read-only, context-consuming support tool. It is not a partition mechanism, truth store, mutation authority, or efficient substitute for structured state.

## Primary style guide

- `00_Meta/00_AGE_STYLE_GUIDE.md`

The AGE Style Guide requires definition-before-use, visible process, ordered and unordered lists, property-sheet examples, calculations where useful, diagrams where useful, two-column ordinary body prose in PDF exports, full-width tables, full-width diagrams, full-width code blocks, Addendum sections with glossary and citations, and preservation of source material under `_resource/`.

## Primary documents

- `00_Executive/01_AGE_Technical_Executive_Summary_Pass2.md`
- `10_White_Papers/00_AGE_Aggregated_Technical_White_Papers_Pass2.md`

The Markdown filenames preserve earlier source lineage where useful. The contents are now Pass 5 no-top-level-breaks and PDF-ready.

## PDF exports included in this archive

- `90_PDF_Exports/AGE_Technical_Executive_Summary_Pass5_NoTopLevelBreaks_20260628.pdf`
- `90_PDF_Exports/AGE_Aggregated_Technical_White_Papers_Pass5_NoTopLevelBreaks_20260628.pdf`

The PDFs use two columns for ordinary body prose. Tables, diagrams, illustrations, and code blocks are rendered full-width.

## Resource directory

- `_resource/origin_branch/Archive.zip`
- `_resource/origin_branch/extracted/`
- `_resource/style_guides/00_AGE_STYLE_GUIDE.md`
- `_resource/style_guides/00_SH44SER_STYLE_GUIDE.md`
- `_resource/comparison_whitepapers/`
- `_resource/resource_inventory/00_Resource_Inventory.md`

The origin branch remains retained byte-for-byte as `_resource/origin_branch/Archive.zip` and extracted for review under `_resource/origin_branch/extracted/`.

## Individual subsystem white papers

- `10_White_Papers/01_Core_Runtime_and_State_Authority.md`
- `10_White_Papers/02_Property_Sheets_and_State_Model.md`
- `10_White_Papers/03_Partitions_Database_Boundaries_and_State_Authority.md`
- `10_White_Papers/04_Time_Location_and_Causal_Cohesion.md`
- `10_White_Papers/05_AGEScript_Event_Generators_and_Consequence.md`
- `10_White_Papers/06_LMS_Graph_CAL_and_Rules_Authority.md`
- `10_White_Papers/07_Multiplayer_Branching_and_Troupe_Isolation.md`
- `10_White_Papers/08_Role_Runtime_Actors_and_Output_Modality.md`
- `10_White_Papers/09_Database_Event_Sourcing_and_Service_APIs.md`
- `10_White_Papers/10_Semantic_QA_Replay_and_Certification.md`
- `10_White_Papers/11_Worked_Dagon_Style_Runtime_Trace.md`
- `10_White_Papers/12_MVP_Implementation_Roadmap_and_Evaluation.md`

## Specifications

- `20_Specifications/01_Property_Sheet_and_Runtime_Packet_Reference.md`
- `20_Specifications/02_AGEScript_Reference_Sketch.md`
- `20_Specifications/03_QA_Audit_Pack_Reference.md`

## Diagrams

Graphviz DOT sources and PNG renders are retained in `assets/diagrams/`.

## Pass 5 correction

1. The partition paper no longer places RAG in the title.
2. The main documents state that retrieval consumes input context and should be budgeted.
3. Structured state reads are preferred over retrieval when the state model can answer directly.
4. Retrieval results cannot mutate state, bypass visibility, cross troupe boundaries, or override partition authority.
5. The PDFs are regenerated from the corrected Markdown and HTML sources and included inside `90_PDF_Exports/`.

## Pass 5 PDF layout correction

The AGE Style Guide no longer requires page breaks before top-level sections. The PDFs retain a table of contents and cover-page breaks, but ordinary top-level sections continue in document flow unless a table, diagram, code block, or natural pagination requires a new page.


## Pass 6 Layout Correction

Pass 6 returns the PDF exports to single-column body prose. The prior two-column export could place a heading in one column while its immediate example, table, or code block was forced below as a full-width block. That behavior broke the effective keep-with-next / keep-with-children relationship needed for technical reference material.

The archive retains full-width diagrams, tables, and code blocks as distinct visual material, but ordinary prose now flows in one column for reliable reading order.
