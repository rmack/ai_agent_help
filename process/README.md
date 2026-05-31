# AI-Assisted Development Process

This directory contains process-level documents for using AI coding agents in a disciplined software development workflow.

These documents explain the operating model behind the more tactical wizard, templates, and organization-facing docs elsewhere in the repository.

For most developers, the concise starting point is the [Engineering Playbook for AI Usage](../docs/Engineering_Playbook_for_AI_Usage.md). The process documents in this directory provide the deeper model behind that playbook.

## Documents

| Document | Purpose |
| --- | --- |
| `ai_divergence_control.md` | Overview of AI divergence as the failure mode controlled through human ownership, patterns, verification, review, tests, documentation, and stop conditions. |
| `ai_development_process_overview.md` | Detailed operating model for AI-assisted development, including architecture-first planning, workflow modes, validation gates, stop conditions, and durable memory. |
| `ai_development_workflow.md` | Shorter practical workflow for moving from discussion to scoped implementation, review, validation, and commit. |

## How To Use

Use `ai_divergence_control.md` after the playbook to understand why the process treats AI output as provisional and how the workflow controls divergence.

Use `ai_development_process_overview.md` when defining or explaining the overall process.

Use `ai_development_workflow.md` when you need a compact checklist for turning a discussion into an implementation handoff.

Use the [Engineering Playbook for AI Usage](../docs/Engineering_Playbook_for_AI_Usage.md) when you need the shorter day-to-day operating standard for engineers.

For interactive AI-agent workflow routing, use `../ai_usage_wizard/`.
