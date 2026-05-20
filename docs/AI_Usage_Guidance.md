# AI Usage Guidance (Software Development)

## 1. Purpose

This document provides practical guidance for using AI tools in software development in a way that complies with organizational policy and aligns with engineering standards.

This guidance is tool-agnostic and applies to any AI-assisted development tool. Tool-specific workflows may vary, but the principles, controls, and expectations remain consistent.

## 2. AI Usage Modes

AI may be used in different modes. The mode determines how it should be applied and what level of control is required.

### Exploration Mode

Used to:

- refine requirements
- explore architecture and design
- evaluate tradeoffs
- understand unfamiliar code

In this mode, AI is used to expand understanding, not produce final solutions.

Guidelines:

- iterate and explore multiple approaches
- challenge assumptions
- treat outputs as suggestions, not answers

### Execution Mode

Used to:

- implement or modify code
- run commands and workflows
- update configurations or documentation

In this mode, AI is acting on defined intent and must be tightly controlled.

Guidelines:

- operate within clearly defined scope
- validate all outputs
- ensure alignment with standards and architecture

### Key Principle

AI may be used to explore ambiguity, but must not silently resolve it.

Do not proceed to implementation until:

- requirements are sufficiently defined
- constraints are clear
- expected outcomes are understood

Transition from exploration mode to execution mode must be explicit.

## 3. When to Use AI

AI may be used to support development across multiple activities:

- requirements and design exploration
- architecture analysis and tradeoff evaluation
- scoped code implementation and refactoring
- test generation
- debugging assistance
- code and logic review
- command execution (build, test, lint, etc.)
- documentation (PRs, repository documentation, AGENTS.md)

AI should be used to accelerate well-defined work, not to replace decision-making.

## 4. Preparing to Use AI

Effective AI usage depends on clear inputs.

Before prompting:

- understand the problem
- define the goal
- identify scope and boundaries
- identify constraints:
  - architecture
  - standards
  - data contracts
- gather relevant context

Poorly defined inputs will produce unreliable outputs.

## 5. Prompting Practices

Use structured prompts to reduce ambiguity:

```text
Goal:
Scope:
Constraints:
Acceptance Criteria:
```

Guidelines:

- be explicit and specific
- constrain outputs to existing patterns
- avoid open-ended requests
- prefer incremental prompts over large requests

Well-structured prompts produce more predictable and usable results.

## 6. Working Iteratively

AI-assisted development should be iterative.

- start with small steps
- validate each result before proceeding
- refine prompts based on output
- avoid large one-shot generation

Breaking work into smaller steps improves control and reduces risk.

## 7. Reviewing AI Output

All AI-generated or AI-assisted outputs must be reviewed before acceptance.

Reviewing is not optional and must include:

- inspection of all changes (diffs)
- verification of correctness
- alignment with standards and architecture
- identification of unintended changes
- consideration of edge cases

Do not assume correctness based on structure or readability.

Developers are responsible for all AI-assisted outputs, including correctness, behavior, performance, and downstream effects.

## 8. Validation and Testing

All changes must be validated at multiple levels.

### Unit Testing

Validates correctness of isolated logic.

- covers edge cases and failure conditions
- ensures individual components behave as expected
- typically fast and deterministic

### Smoke Testing

Validates that the system or pipeline runs successfully at a high level.

- confirms no major failures or crashes
- ensures core functionality is intact
- verifies that key workflows execute successfully

Smoke tests answer: “Does the system run?”

### Regression Testing

Validates that changes have not unintentionally altered expected behavior.

- compares outputs against known baseline artifacts
- detects unintended changes in system behavior
- is critical for systems with deterministic outputs

Regression tests answer: “Did we change something we didn’t intend to?”

### Code Reviews

Perform the required code reviews based on the changes made.

- Security
- Logic
- performance
- Correctness
- Patterns followed
- Etc

### General Principles

- passing tests do not guarantee correctness
- tests validate behavior under specific conditions, not full system correctness
- validate actual outputs, not just execution
- use regression testing where output stability is required

## 9. Working Within Architecture and Standards

AI must operate within established system constraints.

- follow existing architecture and patterns
- respect data contracts and schemas
- maintain consistency across the system

All changes must follow repository-defined rules and constraints (e.g., AGENTS.md).

Do not:

- introduce new patterns without approval
- infer system design from isolated code

## 10. Managing Scope and Changes

Changes must be controlled and reviewable.

- keep changes small and bounded
- isolate modifications

Changes must be:

- minimal
- isolated
- reviewable

If changes become too large:

- break them into smaller steps
- or restart with tighter scope

Large, uncontrolled changes increase risk and reduce review quality.

## 11. Executing Commands and Workflows

AI may be used to execute commands and assist with workflows.

- run local commands (build, test, lint, etc.)
- assist with development workflows

Guidelines:

- verify what commands were executed
- confirm results match expectations
- do not assume successful execution implies correctness

Execution success must always be validated against expected outcomes.

## 12. Environment Validation

Before executing commands or making changes:

- verify read access
- verify write access
- verify command execution

If the environment behaves unexpectedly:

- stop work
- isolate the issue
- resolve before continuing

Proceeding in an unstable environment increases risk of incorrect results.

## 13. Data Handling

AI tools must not be used to expose sensitive information.

Do not include:

- secrets or credentials
- customer or regulated data
- confidential information

Use:

- sanitized examples
- synthetic data

## 14. Cost-Aware Usage

AI usage must be efficient and intentional.

- avoid unnecessary or excessive queries
- prefer scoped interactions over large exploratory requests
- reuse context when appropriate
- select the appropriate tool or model for the task

Efficient usage reduces cost without impacting productivity.

## 15. Common Pitfalls

- overly broad prompts
- relying on AI to resolve ambiguity
- accepting output without review
- generating inconsistent patterns
- missing edge cases
- relying on AI memory instead of documentation

## 16. Quick Checklist

Before submitting changes:

- Requirements are clear
- Scope is defined
- Output is reviewed and understood
- Unit, smoke, and regression tests have been considered or executed
- Changes follow standards and architecture
- No sensitive data has been exposed
