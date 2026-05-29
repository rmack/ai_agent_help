# Engineering Playbook for AI Usage

## Purpose

This playbook defines how engineers use AI tools to support software development while maintaining code quality, architectural integrity, and operational control.

This playbook is tool-agnostic and applies to any AI-assisted development tool. Tool-specific workflows may vary, but the principles and expectations remain consistent.

## Core Principles

- Engineers remain responsible for all outputs generated with AI tools.
- AI is used to accelerate development, not replace engineering judgment.
- Code must remain understandable, maintainable, and aligned with established architecture.
- Consistency and control take precedence over speed.

## Operating Model

### Role Definition

- Engineer = architect, reviewer, and decision-maker.
- AI = assistant for implementation and exploration.

### Source of Truth

- Repository = system of record.
- `AGENTS.md` = rules and constraints.
- Documentation = architecture and decisions.
- AI threads = temporary working context.

## Workflow

1. Define the goal clearly.
2. Request a plan for non-trivial changes.
3. Execute changes in small, scoped steps.
4. Review all diffs carefully.
5. Run validation, including tests and commands.
6. Accept or iterate.

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

## Common Failure Modes

- Overly large or unfocused tasks.
- Blind acceptance of generated code.
- Misinterpreting local code patterns as standards.
- Relying on AI context instead of documentation.
