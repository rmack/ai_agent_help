# Phase 1: CONOPS

## Purpose

Understand how the system should operate before discussing software structure.

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

## Produce

Use `templates/conops.md` and produce:

- problem / mission
- users / actors / systems
- primary workflows
- operating assumptions
- success criteria
- failure scenarios
- constraints
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
