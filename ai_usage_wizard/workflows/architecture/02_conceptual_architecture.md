# Phase 2: Conceptual Architecture

## Purpose

Identify major concepts, capabilities, boundaries, and responsibilities without choosing implementation details yet.

Conceptual architecture turns the CONOPS into major system ideas. It should avoid specific files, frameworks, cloud services, or deployment choices unless those are fixed constraints.

## Input

Use the accepted CONOPS from Phase 1.

## Questions

1. What major capabilities are required?
2. What major conceptual components are needed?
3. What responsibility does each component own?
4. What system boundaries exist?
5. What external systems or actors are involved?
6. What data or events move through the system?
7. What should remain decoupled?
8. What major risks or tradeoffs are visible?

## Produce

Use `templates/conceptual_architecture.md` and produce:

- major capabilities
- major components
- responsibilities
- system boundaries
- high-level data/event flow
- external systems
- risks/tradeoffs
- open questions

## Stop / Continue

After producing the conceptual architecture, ask:

```text
Does this conceptual model look right?

Choose one:
1. Revise Conceptual Architecture
2. Continue to Logical Architecture
3. Stop and summarize what we have
```
