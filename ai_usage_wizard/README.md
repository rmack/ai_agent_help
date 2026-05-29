# AI Usage

This directory provides a portable, text-based wizard for AI-assisted development.

It is designed so the user can type a short command such as:

```text
read ai_usage_wizard
```

The agent should then guide the user through the correct workflow instead of expecting the user to remember the process.

## Two Audiences

This package has two parts:

- `human/` - readable overview and quick-start guidance for developers.
- `agent/` - execution rules that tell an AI agent how to run the process step by step.

The agent should use both, but should primarily follow the instructions in `agent/` and the selected workflow files.

## Standard Startup Behavior

When the user says `read ai_usage_wizard`, `use ai_usage_wizard`, `start ai_usage_wizard`, or similar, the agent must:

1. Read `ai_usage_wizard/AGENTS.md`.
2. Read `ai_usage_wizard/agent/wizard_behavior.md`.
3. Present the workflow menu from `ai_usage_wizard/start_here.md`.
4. Let the user select an option by number or short description.
5. Route to the matching workflow.
6. Ask the next focused question for that workflow.
7. Do not implement until workflow, scope, mode, and validation expectations are clear.

## Main Files

- `AGENTS.md` - agent operating contract.
- `start_here.md` - first user-facing menu.
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
