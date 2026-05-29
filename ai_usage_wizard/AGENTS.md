# AI Usage Agent Instructions

This file defines how an AI agent should use the `ai_usage_wizard/` directory.

## Core Behavior

When the user asks to use or read `ai_usage_wizard`, do not dump the whole process. Start the wizard.

You must:

1. Read `ai_usage_wizard/README.md`.
2. Read `ai_usage_wizard/start_here.md`.
3. Read `ai_usage_wizard/agent/wizard_behavior.md`.
4. Use `ai_usage_wizard/workflow_selector.md` to classify the session.
5. Read the selected workflow's `README.md` and phase files.
6. Follow `ai_usage_wizard/agent/phase_control.md` for multi-phase workflows.
7. Use `ai_usage_wizard/definition_of_done.md` before closing implementation work.
8. Use `ai_usage_wizard/templates/thread_summary.md` when summarizing durable context.

## Do Not Begin Implementation Until

- workflow is selected
- mode is clear: exploration, execution, review, or summary
- scope is clear enough for the selected workflow
- validation expectations are identified
- stop conditions are known

## Interaction Style

- Present choices when the user may not remember options.
- Ask focused questions, not broad open-ended questions.
- Do not ask the user to repeat information already provided.
- For multi-phase workflows, pause between phases and ask whether to revise or continue.
- Keep the user in control of scope and decisions.
- Treat the developer as the decision-maker.

## Process Weight

Classify each task as:

- Lightweight - small, low-risk, localized work.
- Standard - normal development work with moderate uncertainty.
- Heavyweight - architecture, security, data, dependency, CI/CD, or broad impact work.

Use `ai_usage_wizard/process_weights.md` for guidance.

## Stop Conditions

Stop and ask for direction if:

- requirements are unclear
- the task expands beyond selected workflow
- architecture impact is larger than expected
- a new dependency seems necessary
- security or sensitive data risk appears
- tests fail for unclear reasons
- the agent is guessing

## Durable Memory

If the discussion contains reusable decisions, architecture notes, patterns, or tangents, recommend creating a Markdown thread summary.
