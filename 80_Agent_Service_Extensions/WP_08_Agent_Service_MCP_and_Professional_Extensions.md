# White Paper 08 — Agent Service, MCP, and Professional Extensions

## Plain definition

Agent Service is the later layer that allows qualified roles to perform bounded external actions through APIs or MCP gateways.

## Problem addressed

Some future AGE roles may need to do more than speak: schedule, file, notify, create tickets, update systems, or coordinate workflows. That is not safe until Role Service, CAL, permissions, and audit are mature.

## Responsibility

Agent Service owns action envelopes, external tool permissions, API/MCP integration, approval gates, revocation, audit, and human oversight.

## Relation to other subsystems

Agent Service depends on Role Service for actor identity and permissions, CAL for source-grounded guidance where needed, Semantic QA for behavior checks, and governance for authority boundaries.

## Reward

AGE can eventually support serious-play operations, enterprise workflows, and bounded professional support tasks.

## Risk

External action creates liability and safety exposure. A wrong answer is one risk; a wrong action is larger.

## Mitigation

Keep Agent Service out of MVP. Require explicit permissions, narrow action scopes, human approval for consequential actions, replay, revocation, and audit.

## Success criteria

A qualified role can perform a bounded external action only when authorized, logged, reviewable, and reversible or accountable.
