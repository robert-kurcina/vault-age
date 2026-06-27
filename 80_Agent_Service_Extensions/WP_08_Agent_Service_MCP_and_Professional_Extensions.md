# White Paper 08 - Agent Service, Model Context Protocol, and Professional Extensions

## Purpose

The Amazing Game Engine [AGE] may later include Agent Service. Agent Service is the subsystem that allows authorized roles to perform external actions. Model Context Protocol [MCP] is a protocol pattern for connecting model systems to tools and external resources. An application programming interface [API] is a defined software interface used to communicate with a system or service.

Agent Service is not part of the first minimum viable product. A minimum viable product [MVP] is the smallest product that proves the core loop. AGE must prove state authority, rules arbitration, roles, output verification, and replay before it allows external action.

## Why Agent Service Is Separate

A role that speaks is one risk class. A role that acts outside the game or corpus is another. Sending email, booking a calendar event, editing a document, filing a form, querying a private database, initiating a purchase, updating a ticket, or calling a professional system creates real-world consequence. The AGE architecture must not allow external action merely because a role generated persuasive instructions.

Agent Service therefore requires explicit authorization, tool boundaries, approval steps, audit logs, rollback planning where possible, and human accountability.

## Relationship to Role Service

Role Service defines who the actor is and what it may claim. Agent Service defines what the actor may do through external tools. The two services must remain separate. A legal assistant role may summarize a case corpus without having permission to send filings. A scheduling assistant may propose times without having permission to confirm a meeting. A game NPC may threaten to call guards without having permission to alter real client data.

A Role Semantic Contract should list whether a role has any external-action capability. If it does, the Agent Service contract should define allowed tools, data access, approval requirements, rate limits, logging, and failure handling.

## Professional Extensions

AGE's professional extension path depends on LMS-Graph and the Corpus Arbitration Layer. A professional corpus may include codes, standards, regulations, case law, institutional procedures, or licensing rules. The system can retrieve, weigh, and explain sources. It can identify conflicts and decision points. It should not present itself as the licensed professional unless the deployment has the legal, organizational, and human authority to support that use.

Professional domains raise the stakes. A wrong game ruling can be corrected by the Referee. A wrong legal, medical, engineering, financial, or safety answer can harm people. AGE should therefore treat professional expansion as a later stage requiring stronger source licensing, domain review, audit, semantic quality assurance, privacy controls, and jurisdiction modeling.

## Tool Boundary Procedure

External tool calls should follow a strict order.

1. Identify the role and its contract.
2. Identify the requested external action.
3. Check whether the action is within allowed tools.
4. Check whether required data is available and permitted.
5. Present the action plan and consequence to the human where approval is required.
6. Execute only after approval or within preauthorized bounds.
7. Record tool call, input, output, state change, and human approval.
8. Report success, failure, uncertainty, and rollback options.

The tool call should never be hidden inside generated prose.

## Example

A campaign author asks an authoring assistant to publish a new adventure packet. The role may assemble files, run validation, and present a publication checklist. It should not publish to a marketplace until the author approves the exact package, version, price, rights statement, and public description. The Agent Service records the approval and action.

In a professional setting, a compliance assistant may draft a report from a source-grounded arbitration envelope. It should not file the report with an agency unless the deployment contract, user authority, and approval workflow allow that action.

## Risks

Agent Service increases attack surface, privacy risk, legal risk, and user trust risk. A prompt-injected document could try to make a role call tools. A user could ask a role to exceed its authority. A tool could return ambiguous or dangerous data. A professional workflow could be mistaken for licensed advice.

The mitigation is to keep Agent Service out of the first MVP, require explicit contracts, use least-privilege tool access, log all external actions, and require human approval for high-impact operations.

## External Action Classes

External actions should be classified by risk. Read-only lookup is lower risk than writing to a system. Drafting is lower risk than sending. Local game-state action is lower risk than real-world action. Financial, legal, medical, safety, identity, and public communication actions are high risk. AGE should not use one permission model for all tools.

A role that can read a calendar is not automatically allowed to schedule a meeting. A role that can draft an email is not automatically allowed to send it. A role that can retrieve a regulation is not automatically allowed to file a compliance document.

## Approval Design

Human approval should be specific. A vague prior statement such as "handle this for me" should not authorize every downstream action. The approval prompt should show the action, target system, data to be sent, expected consequence, reversible or irreversible status, and audit record. The user should approve the exact operation or delegate a clearly bounded class of operations.

## Professional Boundary

Professional extension should begin with reference and drafting, not autonomous practice. AGE may retrieve sources, assemble an arbitration envelope, draft a memo, or prepare a checklist. It should not present the output as final professional judgment unless the deployment has the required human and institutional controls. This boundary protects users and protects the product.

## Success Criteria

Agent Service succeeds only when an external action can be traced to a role contract, permission check, human approval policy, tool call, result, and audit record. Until that standard is met, AGE should keep external action out of scope.
