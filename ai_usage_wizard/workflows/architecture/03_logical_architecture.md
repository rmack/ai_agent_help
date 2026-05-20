# Phase 3: Logical Architecture

## Purpose

Convert the conceptual model into software responsibilities, modules, contracts, and validation expectations.

Logical architecture defines how the conceptual design becomes software structure. It describes modules, services, jobs, interfaces, schemas, state ownership, validation, and test strategy without yet deciding where the pieces run or which infrastructure hosts them.

## Input

Use the accepted CONOPS and conceptual architecture.

## Questions

1. What modules, services, functions, jobs, or components are needed?
2. What are their responsibilities?
3. What interfaces or contracts exist between them?
4. What data models or schemas are involved?
5. What state is owned, read, written, or transformed?
6. What validation rules are required?
7. What should be deterministic?
8. What should fail loudly?
9. What test strategy is appropriate?

## Produce

Use `templates/logical_architecture.md` and produce:

- modules/services/units
- responsibilities
- interfaces/contracts
- data models/schemas
- state ownership / transitions
- validation rules
- deterministic behavior
- error handling expectations
- test strategy
- open questions

## Stop / Continue

After producing the logical architecture, ask:

```text
Does this logical architecture look right?

Choose one:
1. Revise Logical Architecture
2. Continue to Physical Architecture
3. Stop and summarize what we have
```
