# AI Usage

This directory provides a portable, text-based wizard for AI-assisted development.

It is designed so the user can type a short command such as:

```text
read ai_usage_wizard
```

The agent should then guide the user through the correct workflow instead of expecting the user to remember the process.

The wizard is an experimental learning aid and reference tool. It can help users reason through the process, but it is not a replacement for human understanding, judgment, or responsibility. Users should adapt the guidance to their own project, team, and environment.

## Two Audiences

This package has two parts:

- `human/` - readable overview and quick-start guidance for developers.
- `agent/` - execution rules that tell an AI agent how to run the process step by step.

The agent should use both, but should primarily follow the instructions in `agent/` and the selected workflow files.

## Standard Startup Behavior

When the user says `read ai_usage_wizard`, `use ai_usage_wizard`, `start ai_usage_wizard`, or similar, the agent must:

1. Read `ai_usage_wizard/AGENTS.md`.
2. Read `ai_usage_wizard/README.md`.
3. Read `ai_usage_wizard/start_here.md`.
4. Read `ai_usage_wizard/agent/wizard_behavior.md`.
5. Use `ai_usage_wizard/workflow_selector.md` to classify the session.
6. Present the workflow menu from `ai_usage_wizard/start_here.md` when the user has not already provided a specific task.
7. Let the user select an option by number or short description.
8. Read the selected workflow's `README.md` and phase files.
9. Ask the next focused question for that workflow.
10. Follow `ai_usage_wizard/agent/phase_control.md` for multi-phase workflows.
11. Do not implement until workflow, scope, mode, validation expectations, and stop conditions are clear.
12. Use `ai_usage_wizard/definition_of_done.md` before closing implementation work.
13. Use `ai_usage_wizard/templates/thread_summary.md` when summarizing durable context.

## Main Files

- `AGENTS.md` - agent operating contract.
- `start_here.md` - first user-facing menu.
- `workflow_selector.md` - workflow classification and routing guidance.
- `process_weights.md` - lightweight, standard, and heavyweight task classification.
- `definition_of_done.md` - closeout checklist for implementation work.
- `human/overview.md` - human-readable process explanation.
- `human/quick_start.md` - short human quick start.
- `agent/execution_rules.md` - common execution rules for all workflows.
- `agent/phase_control.md` - how to move through multi-phase workflows.
- `agent/wizard_behavior.md` - how to behave like a text-based wizard.
- `workflows/` - workflow-specific execution instructions.
- `templates/` - reusable output templates.

## User Reminder

You should not need to remember all workflows. Start with:

```text
read ai_usage_wizard
```

Then follow the wizard.

The wizard can help you choose and follow a workflow, but you remain responsible for understanding the process and deciding what is appropriate for your situation.
