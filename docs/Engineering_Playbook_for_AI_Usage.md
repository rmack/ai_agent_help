# Engineering Playbook for AI Usage

## Purpose

This playbook defines how engineers use AI tools to support software development while maintaining code quality, architectural integrity, and operational control.

This playbook is tool-agnostic and applies to any AI-assisted development tool. Tool-specific workflows may vary, but the principles and expectations remain consistent.

This playbook is the concise engineer-facing operating standard. For the fuller process model, workflow prompts, phase guidance, and examples, see `process/ai_development_process_overview.md`.

## Core Principles

- Engineers remain responsible for all outputs generated with AI tools.
- AI is used to accelerate development, not replace engineering judgment.
- Code must remain understandable, maintainable, and aligned with established architecture.
- Consistency and control take precedence over speed.

## Operating Model

### Role Definition

- Engineer = architect, reviewer, and decision-maker.
- AI       = assistant for implementation and exploration.

### Source of Truth

- Repository    = system of record.
- `AGENTS.md`   = rules and constraints. (Or agent specific files like CLAUDE.md)
- Documentation = architecture and decisions.
- AI threads    = temporary working context.

## Workflow

1. Define the goal clearly.
2. Request a plan for non-trivial changes.
3. Execute changes in small, scoped steps.
4. Review all diffs carefully.
5. Run validation, including tests and commands.
6. Accept or iterate.

## Workflow Modes

Engineers should choose the AI workflow based on the intent of the task. Do not use the same interaction pattern for every kind of work.

Common modes include:

- New project or major architecture design.
- Enhancement of an existing project.
- Bug fix or defect investigation.
- Technical debt or refactor with no intended behavior change.
- Architecture review.
- Code review.
- CI/CD, build, release, or deployment review.
- Ideation, brainstorming, or option comparison.
- Thread summary or durable memory capture.

Each mode has different expectations for planning, validation, review, and stop conditions.

## Exploration vs Execution

Exploration mode is for unclear requirements, architecture, tradeoffs, options, or risks. In exploration mode, AI should help reason, compare, question, and summarize. It should not make implementation changes unless the engineer explicitly moves the task into execution.

Execution mode is for scoped implementation. Before execution, the goal, scope, constraints, acceptance criteria, validation expectations, and stop conditions must be clear enough to support reviewable changes.

## Plan-First Requirements

A plan must be created before modifying:

- Schemas or contracts.
- Cross-module logic.
- Pipelines or stage flows.
- Performance-critical paths.
- Architectural components.

## Task Scoping

- Changes must be small and bounded.
- Avoid broad or ambiguous prompts.
- Break work into:
  - Ideation.
  - Implementation.
  - Cleanup.
  - Testing.

## Human Gates

Engineers should deliberately pause at important decision points instead of letting AI carry work smoothly from idea to implementation.

Gate depth should match task risk. Trivial edits may only require scope, diff,
and validation review. Higher-risk work requires stronger gates before AI moves
from exploration into execution.

Common risk tiers:

- Trivial: documentation copy edits, comments, formatting within an approved
  scope, or other changes with no intended behavior impact.
- Normal: localized implementation changes with clear requirements, existing
  patterns, and limited downstream impact.
- High-risk: schema, contract, architecture, security, deployment, dependency,
  data-handling, pipeline, performance-critical, or cross-module changes.
- Regulated or sensitive: work involving customer data, confidential data,
  regulated data, credentials, production access, compliance controls, or
  externally visible commitments.

Required gates for normal, high-risk, regulated, or sensitive work include:

- Problem understanding before architecture or design.
- Architecture approval before code.
- Pattern approval before introducing or extending implementation patterns.
- Scope approval before file edits.
- Diff review after changes.
- Validation review after tests or checks.
- Documentation capture before closing the thread, PR, or handoff.

For trivial work, engineers may use a lighter gate set, but still remain
responsible for reviewing the diff, validating the result, and ensuring the
change stays within scope.

## Validation Requirements

All changes must be validated through:

- Code review, including diff inspection.
- Execution of relevant commands and tests.
- Review of generated or deterministic artifacts when outputs are expected to remain stable.

Developers must:

- Understand what tests validate.
- Not rely solely on passing results.
- Confirm that validation evidence is strong enough for the specific task.

## Testing Philosophy

Two levels of testing are required:

### Unit Testing

- Validates correctness of isolated logic.
- Covers edge cases and failure conditions.
- Requires reviewing the tests for meaningful assertions.

### Smoke Testing

- Validates system-level or stage-level behavior.
- Confirms pipeline and integration integrity.
- Confirms fail-loud behavior for development-time execution blocks where
  hidden failure would mask correctness issues.

### Regression and Golden Artifact Testing

- Validates that expected behavior did not change unintentionally.
- Compares deterministic outputs against known-good golden artifacts when stable
  outputs are part of the contract.
- Requires reviewing artifact diffs before accepting regenerated artifacts.

### General Principles

- Do not create unnecessary tests.
- Prefer extending existing test coverage.
- Validate outputs, not just execution.
- Passing tests are evidence, not proof of full correctness.

## Review Loop

AI-generated work should be reviewed through a deliberate loop:

1. The engineer reviews the diff against the original request, handoff,
   architecture, and acceptance criteria.
2. A secondary agent review is used for non-trivial or risky AI-generated
   changes.
3. Agent findings are compared with the engineer's own findings.
4. Valid findings are sent back to the implementation agent for evaluation and
   fixes.
5. The engineer reviews the fixes and may request another independent agent
   review before acceptance.

## Change Control

- Changes must be:
  - Minimal.
  - Isolated.
  - Reviewable.
- The following are not permitted:
  - Silent behavior changes.
  - Schema drift.
  - Unnecessary formatting changes.

## Stop Conditions

AI-assisted work must stop and return to engineer decision-making when:

- Requirements are unclear.
- Scope expands beyond the approved task.
- Architecture impact is larger than expected.
- A new dependency appears necessary.
- Security, permissions, deployment, or data handling risk appears.
- Tests fail for unclear reasons.
- Validation results are ambiguous.
- Existing patterns are inconsistent or poor.
- The AI is guessing.

When a stop condition occurs, summarize what changed, what triggered the stop, what decision is needed, and the available options before continuing.

## Environment Validation

Before executing work:

- Confirm read access.
- Confirm write access.
- Confirm command execution.

If unexpected behavior occurs:

- Stop work.
- Isolate the issue.
- Restart with a clean context.

## Accountability

Developers are responsible for:

- Correctness.
- Behavior changes.
- Performance impact.
- Downstream effects.

AI-generated output does not reduce accountability.

## Cost Awareness

- AI usage must be intentional and efficient.
- Avoid unnecessary or excessive usage.
- Prefer scoped interactions over large exploratory prompts.
- Select appropriate tools/models for the task.

## Knowledge Management

- Do not rely on AI thread history.
- Persist knowledge in:
  - Documentation.
  - Architecture records.
  - Decision logs.
- Capture useful thread context in Markdown summaries when discussions create reusable decisions, patterns, open questions, or future work.
- Promote durable repository-specific AI rules and patterns into `AGENTS.md` when future agents should follow them.

## Common Failure Modes

- Overly large or unfocused tasks.
- Blind acceptance of generated code.
- Misinterpreting local code patterns as standards.
- Relying on AI context instead of documentation.
