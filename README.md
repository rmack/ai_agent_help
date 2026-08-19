# AI Agent Help

This repository contains a lightweight documentation kit for using AI coding agents in a disciplined software development workflow.

The goal is to help developers and organizations get useful assistance from AI without losing control of requirements, architecture, implementation scope, validation, policy, or final decisions.

## What This Repo Is

This is not an application or library. It is a collection of Markdown process documents, agent instructions, workflow guides, and templates.

The repository is organized around three related purposes:

1. Development workflow and process
2. Policy and organizational documentation
3. `ai_usage_wizard`, a guided teaching and workflow aid for working with AI agents

Use it to:

- guide AI-assisted development sessions
- choose the right workflow for a task
- separate exploration from execution
- keep implementation work scoped and reviewable
- define validation expectations before making changes
- explain policy, guidance, and engineering expectations for AI usage
- capture durable context outside temporary chat threads
- create repository-based WBS Streams and bounded Work Packages for durable execution
  and closeout
- provide reusable `AGENTS.md` and `CLAUDE.md` templates for other repositories

## Start Here: Developer Reading Order

Developers should start with these four documents:

1. [Engineering Playbook for AI Usage](docs/Engineering_Playbook_for_AI_Usage.md)

   A concise day-to-day operating standard for using AI during software development.

2. [AI Divergence Control Overview](process/ai_divergence_control.md)

   A short overview of why AI output is treated as provisional until verified, and how patterns, review, tests, documentation, and stop conditions make divergence visible and correctable.

3. [AI-Assisted Development Process Overview](process/ai_development_process_overview.md)

   The full process model behind the playbook, including workflow modes, architecture-first planning, gates, validation, stop conditions, and durable memory.

4. [AI Development Workflow](process/ai_development_workflow.md)

   A practical workflow for moving from discussion to scoped implementation, review, validation, and handoff.

After those, use [`ai_usage_wizard/`](ai_usage_wizard/) when you want an AI agent to guide the process interactively.


## Operating Model

This repo is easiest to understand as three layers that support each other.

### 1. Development Workflow and Process

The process layer defines how developers should use AI during software work. It covers architecture-first thinking, exploration vs execution, workflow modes, validation gates, stop conditions, durable memory, and reviewable implementation handoffs.

Primary locations:

- [`process/`](process/)
- [`process/ai_divergence_control.md`](process/ai_divergence_control.md)
- [`process/ai_development_process_overview.md`](process/ai_development_process_overview.md)
- [`process/ai_development_workflow.md`](process/ai_development_workflow.md)
- [`templates/`](templates/)

### 2. Policy and Organizational Documentation

The policy layer describes how an organization can govern AI usage. It separates mandatory policy, practical guidance, engineering playbook material, and lightweight daily reference material.

Primary locations:

- [`docs/`](docs/)
- [`docs/AI_Usage_Policy.md`](docs/AI_Usage_Policy.md)
- [`docs/AI_Usage_Guidance.md`](docs/AI_Usage_Guidance.md)
- [`docs/Engineering_Playbook_for_AI_Usage.md`](docs/Engineering_Playbook_for_AI_Usage.md)
- [`docs/Engineering_Playbook_for_AI_Usage_Quick_Reference.md`](docs/Engineering_Playbook_for_AI_Usage_Quick_Reference.md)

### 3. `ai_usage_wizard`

The wizard layer is a portable, text-based aid that an AI agent can read and follow. It helps teach the workflow by routing a session, asking focused questions, identifying process weight, enforcing phase boundaries, and prompting for validation and closeout.

Primary locations:

- [`ai_usage_wizard/`](ai_usage_wizard/)
- [`ai_usage_wizard/start_here.md`](ai_usage_wizard/start_here.md)
- [`ai_usage_wizard/workflow_selector.md`](ai_usage_wizard/workflow_selector.md)
- [`ai_usage_wizard/agent/`](ai_usage_wizard/agent/)
- [`ai_usage_wizard/workflows/`](ai_usage_wizard/workflows/)
- [`ai_usage_wizard/templates/`](ai_usage_wizard/templates/)
- [`ai_usage_wizard/templates/wbs/`](ai_usage_wizard/templates/wbs/)

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
| [`process/`](process/) | Development workflow and process model for disciplined AI-assisted engineering. |
| [`docs/`](docs/) | Policy and organization-facing AI usage documentation. |
| [`ai_usage_wizard/`](ai_usage_wizard/) | Portable text-based wizard for teaching and guiding AI-agent interaction during real work. |
| [`presentation/`](presentation/) | Slide-deck and PDF presentation assets for explaining the workflow. |
| [`templates/`](templates/) | Reusable agent instruction templates for other repositories. |

## `process/`

This directory contains the process-level material for AI-assisted development.

Start with [process/README.md](process/README.md) for the current process document inventory.

### `process/ai_divergence_control.md`

A short overview of AI divergence as the failure mode the workflow controls.

It emphasizes:

- treating AI-generated work as provisional until verified
- using repeatable patterns as an execution and review surface
- grounding claims in repository evidence, runtime output, docs, or authoritative references
- using tests, deterministic outputs, and golden artifacts as confidence evidence
- stopping when critical assumptions cannot be verified

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

The wizard is an experimental learning aid and reference tool. It is intended to help users understand and apply the process, not to replace human judgment or responsibility. Users should understand the workflow, adapt it to their project and environment, and make the final decisions about what is appropriate.

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
- `ai_usage_wizard/templates/wbs/` - WBS usage guide and reusable Overview, Stream,
  and Work Package templates

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

The Markdown files are the maintained source documents.

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

The materials in this repository are intended to help people learn and practice a disciplined workflow. They are references, not a substitute for understanding the process or making context-specific decisions for a given team, project, or environment.

## License

This repository is licensed under the Creative Commons Attribution 4.0 International License. See [LICENSE.md](LICENSE.md).
