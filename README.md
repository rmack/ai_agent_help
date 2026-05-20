# AI Agent Help

This repository contains a lightweight documentation kit for using AI coding agents in a disciplined software development workflow.

The goal is to help developers get useful assistance from AI without losing control of requirements, architecture, implementation scope, validation, or final decisions.

## What This Repo Is

This is not an application or library. It is a collection of Markdown process documents, agent instructions, workflow guides, and templates.

Use it to:

- guide AI-assisted development sessions
- choose the right workflow for a task
- separate exploration from execution
- keep implementation work scoped and reviewable
- define validation expectations before making changes
- capture durable context outside temporary chat threads
- provide reusable `AGENTS.md` and `CLAUDE.md` templates for other repositories

## Main Contents

```text
.
├── ai_usage_wizard/
├── docs/
├── presentation/
├── process/
└── templates/
```

| Path | Purpose |
| --- | --- |
| [`ai_usage_wizard/`](ai_usage_wizard/) | Portable text-based wizard for routing AI-assisted development work into the right workflow. |
| [`docs/`](docs/) | Organization-facing AI usage policy, guidance, playbook, and quick reference material. |
| [`presentation/`](presentation/) | Slide-deck and PDF presentation assets for explaining the workflow. |
| [`process/`](process/) | Process-level documents that explain the AI-assisted development operating model. |
| [`templates/`](templates/) | Reusable agent instruction templates for other repositories. |

## `process/`

This directory contains the process-level material for AI-assisted development.

Start with [process/README.md](process/README.md) for the current process document inventory.

### `process/ai_development_process_overview.md`

The detailed operating model for AI-assisted development.

It covers:

- human ownership of architecture and decisions
- architecture-first planning
- exploration vs execution modes
- validation gates
- stop conditions
- durable Markdown memory files
- risks of unstructured AI-generated code

### `process/ai_development_workflow.md`

A shorter, practical workflow for moving from discussion to implementation.

It emphasizes:

- defining thread purpose
- clarifying scope and acceptance criteria
- creating handoff Markdown for AI agents
- asking agents to explain their understanding before editing
- executing in small steps
- reviewing diffs
- running appropriate tests
- committing locally when work is validated

## `ai_usage_wizard/`

This is the main reusable package in the repo.

It provides a text-based wizard that an AI agent can read and follow when a user types something like:

```text
read ai_usage_wizard
```

The wizard helps route the session into the correct workflow instead of requiring the user to remember the process.

Key files:

- `ai_usage_wizard/README.md` - package overview
- `ai_usage_wizard/start_here.md` - user-facing workflow menu
- `ai_usage_wizard/AGENTS.md` - agent operating contract
- `ai_usage_wizard/workflow_selector.md` - workflow routing guidance
- `ai_usage_wizard/process_weights.md` - lightweight, standard, and heavyweight task classification
- `ai_usage_wizard/definition_of_done.md` - closeout expectations
- `ai_usage_wizard/human/` - human-facing overview and quick start
- `ai_usage_wizard/agent/` - agent behavior and execution rules
- `ai_usage_wizard/workflows/` - task-specific workflow instructions
- `ai_usage_wizard/templates/` - reusable Markdown output templates

## Available Workflows

The wizard currently supports:

- architecture or new project design
- enhancement of an existing project
- bug fix
- technical debt or refactor
- architecture review
- code review
- CI/CD, build, release, or deployment review
- ideation or brainstorming
- thread summary and Markdown memory capture

Each workflow defines the expected phases, questions, stop conditions, and validation expectations for that kind of work.

## `docs/`

This directory contains organization-facing AI usage documentation for software development.

Start with [docs/README.md](docs/README.md) for the current document inventory and an overview of the components an organization should consider when adopting AI.

Current documents include:

- AI usage policy
- AI usage guidance
- engineering playbook for AI usage
- lightweight engineering quick reference

The Markdown files are the editable source documents. The `.docx` files are document exports for sharing or review.
Word exports are stored under `docs/docx/`.

## `presentation/`

This directory contains presentation material for communicating the AI-assisted development workflow.

Start with [presentation/README.md](presentation/README.md) for the current presentation inventory.

Current assets include:

- a PDF export for viewing and sharing
- a PowerPoint source deck stored under `presentation/pptx/`

## `templates/`

This directory contains reusable repository-level agent instruction templates:

- `templates/AGENTS.md`
- `templates/CLAUDE.md`

Start with [templates/README.md](templates/README.md) for usage notes.

These can be copied into another repository to give AI tools a simple operating contract.

## Basic Usage

To use the wizard in this repository or after copying it into another project, ask the AI agent:

```text
read ai_usage_wizard
```

The agent should load the wizard, present the workflow menu, ask focused questions, and avoid implementation until workflow, scope, mode, validation expectations, and stop conditions are clear.

For broader planning, start with:

```text
Read process/ai_development_process_overview.md and help me apply this process to my project.
```

For a shorter operating checklist, start with:

```text
Read process/ai_development_workflow.md and help me create a handoff for an AI coding agent.
```

## Core Principle

The developer drives the work.

AI assists with exploration, planning, implementation, review, validation, and summarization, but the human remains responsible for requirements, architecture, correctness, security, and final approval.

## License

This repository is licensed under the Creative Commons Attribution 4.0 International License. See [LICENSE.md](LICENSE.md).
