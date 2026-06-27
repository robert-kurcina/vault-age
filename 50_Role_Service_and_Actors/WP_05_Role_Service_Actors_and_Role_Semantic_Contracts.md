# White Paper 05 — Role Service, Actors, and Role Semantic Contracts

## Plain definition

Role Service defines bounded actors. A role is not just a prompt persona; it is a contract for knowledge, behavior, authority, memory, evidence, and permitted action.

## Problem addressed

LLM characters and assistants drift when their behavior is held only in prompt text. AGE roles need durable boundaries: what they know, what they can say, what they can do, what evidence they need, and when they must defer.

## Responsibility

Role Service owns Role Semantic Contracts, role epistemology, permissions, memory scope, behavioral constraints, evidence requirements, refusal/escalation rules, and role audit logs.

## Role Semantic Contract

A Role Semantic Contract defines purpose, audience, scope, knowledge boundaries, allowed claims, prohibited claims, tone/register constraints, tool access, CAL access, memory rules, and verification criteria.

## Role epistemology

Role epistemology defines what the role knows and how it knows it: personal observation, world state, corpus retrieval, author knowledge, table policy, rumor, inference, or hidden engine state. Roles must not leak knowledge outside their epistemic scope.

## Reward

AGE can run NPCs, advisors, tutors, facilitators, authoring helpers, and later professional support roles without treating them as unbounded chatbots.

## Risk

Roles can become too rigid, too generic, or falsely authoritative.

## Mitigation

Use contract versions, evidence rules, CAL references, memory partitions, Semantic QA, and drift detection.

## Success criteria

A role can interact naturally while staying within its knowledge, authority, behavior, and evidence boundaries.
