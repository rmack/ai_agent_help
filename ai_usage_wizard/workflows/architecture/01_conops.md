# Phase 1: CONOPS

## Purpose

Define the operating intent before discussing software structure.

CONOPS describes how the system should work in the real world: the problem, users, workflows, assumptions, success criteria, failure scenarios, and constraints that shape the design.

## Agent Behavior

Ask only the questions needed to build a useful CONOPS. If the user has already provided some answers, do not ask again.

## Questions

1. What problem are we solving?
2. Who are the users, actors, systems, jobs, or external services involved?
3. What are the primary workflows?
4. What does success look like?
5. What failure scenarios matter?
6. What assumptions are we making?
7. What constraints, non-goals, or boundaries exist?
8. What decisions must be made before architecture design can proceed?

## Produce

Use `templates/conops.md` and produce:

- problem / mission
- users / actors / systems
- primary workflows
- operating assumptions
- success criteria
- failure scenarios
- constraints
- non-goals / boundaries
- open questions

## Stop / Continue

After producing the CONOPS summary, ask:

```text
Does this CONOPS look right?

Choose one:
1. Revise CONOPS
2. Continue to Conceptual Architecture
3. Stop and summarize what we have
```
