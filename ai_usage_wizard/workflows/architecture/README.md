# Architecture / New Project Workflow

Use this workflow when starting a new project, designing a major new capability, or creating/reworking architecture.

## Purpose

Move from operating concept to implementation structure without jumping prematurely into code.

## Phase Sequence

1. `01_conops.md`
2. `02_conceptual_architecture.md`
3. `03_logical_architecture.md`
4. `04_physical_architecture.md`
5. `05_architecture_decision_summary.md`

## Agent Rules

- Follow `agent/phase_control.md`.
- Do not skip CONOPS unless the user explicitly asks.
- Do not move to conceptual architecture until CONOPS is accepted or revised.
- Do not move to logical architecture until conceptual architecture is accepted or revised.
- Do not move to physical architecture until logical architecture is accepted or revised.
- Do not propose implementation until physical architecture and validation expectations are clear.

## Initial Wizard Questions

Ask:

```text
Selected workflow: Architecture / New Project
Process weight: Heavyweight unless the user says this is a lightweight prototype.
Mode: Exploration

We will move through phases:
1. CONOPS
2. Conceptual Architecture
3. Logical Architecture
4. Physical Architecture
5. Architecture Decision Summary

Current phase: CONOPS

To begin, answer what you can:
1. What are we trying to build or change?
2. Who or what will use it?
3. What problem should it solve?
4. Is this a prototype, production system, internal tool, or design exploration?
5. Are there constraints I should know about?
```
