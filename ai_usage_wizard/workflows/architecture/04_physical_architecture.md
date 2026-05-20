# Phase 4: Physical Architecture

## Purpose

Map the logical architecture to actual files, folders, tools, dependencies, commands, deployment units, and implementation sequence.

## Input

Use the accepted CONOPS, conceptual architecture, and logical architecture.

## Questions

1. Is there an existing repository or is this a new project?
2. What files or folders likely need to exist or change?
3. What files or areas should not change?
4. What existing patterns must be followed?
5. Are new dependencies required? If yes, pause for approval.
6. What commands should validate the work?
7. What implementation sequence keeps changes reviewable?

## Produce

Use `templates/physical_architecture.md` and produce:

- repository/project structure
- files likely to change
- files that should not change
- dependencies/tools
- validation commands
- implementation sequence
- risks / stop conditions

## Stop / Continue

After producing the physical architecture, ask:

```text
Does this physical architecture and implementation sequence look right?

Choose one:
1. Revise Physical Architecture
2. Create Architecture Decision Summary
3. Move toward implementation planning
4. Stop and summarize what we have
```
