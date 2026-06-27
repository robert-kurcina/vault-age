# White Paper 04B — World Generation, Lazy Ontology, and Overlays

## Plain definition

Lazy ontology lets AGE start with world scaffolding and actualize detail only when needed. Overlays are concern-specific lenses that interpret state and propose consequences.

## Problem addressed

A persistent world needs depth, but fully prebuilding or simulating all detail is wasteful and brittle. AGE separates scaffolded possibility from actualized canonical fact.

## Responsibility

This subsystem defines world scaffolds, actualization triggers, provenance, contradiction checks, overlay proposal rules, technology-level vectors, cultural/law/economy/faction lenses, and living-world interactions.

## Operating model

The world may know that a city has a market district before it knows every shop. A shop becomes canonical when a player visits, an author defines it, an event needs it, CAL references it, or an overlay actualizes it. Once created, it is versioned state.

Overlays inspect relevant partitions and propose effects. For example, a law overlay may restrict weapons in a city; a technology overlay may determine available devices; an economy overlay may alter prices; a religion overlay may change social access. The Bridge Layer validates proposals before mutation.

## Reward

AGE can provide large-world feel with manageable state cost and strong author leverage.

## Risk

Lazy actualization can create contradictions if later detail conflicts with prior scaffold or authored fact.

## Mitigation

Track provenance, actualization reason, scope, overlay source, and contradiction tests.

## Success criteria

AGE can create useful local detail on demand, preserve it as canon, and prevent overlays from silently mutating state.
