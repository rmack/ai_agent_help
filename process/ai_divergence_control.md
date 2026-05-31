# AI Divergence Control Overview

## Purpose

This document explains why this workflow treats AI-generated output as provisional until verified. It is an overview, not a complete treatment of AI risk, software quality, or engineering governance.

The purpose is to make the underlying control model explicit: AI can produce useful work, but it can also diverge from reality, user intent, project architecture, established patterns, or verified system behavior. The workflow exists to make that divergence visible, bounded, reviewable, and correctable before it becomes accepted work.

## Problem Statement

AI-generated output can sound confident while being wrong, incomplete, or misaligned with the project. This includes hallucinated facts, APIs, files, commands, requirements, dependencies, test results, architecture, or implementation details.

The risk is broader than hallucination alone. An AI agent may also misunderstand the user's intent, overfit to a local pattern, ignore an architectural constraint, change behavior outside the intended scope, or produce code that appears valid but does not satisfy the real design goal.

Because of this, AI output must not be treated as authoritative by default.

## Governing Principle

AI-generated work is provisional until verified.

Claims, plans, code, tests, and explanations should be grounded in evidence from the repository, runtime output, project documentation, architecture documents, established patterns, accepted work artifacts, or authoritative external references when external facts are required.

When a critical assumption cannot be verified, the agent should stop, document the uncertainty, and ask for direction rather than proceed confidently.

## Human Role

The human remains the reality anchor for the work.

The human is not merely approving AI output. The human must know enough about the domain, system, architecture, and expected behavior to detect when AI-generated work is plausible but wrong, incomplete, mis-scoped, or inconsistent with project intent.

The process helps the human convert knowledge into reviewable artifacts: architecture notes, logic patterns, design patterns, syntax patterns, test patterns, work breakdown structures, validation expectations, and review criteria. These artifacts give agents concrete boundaries to follow and give reviewers concrete evidence to inspect.

Patterns are foundational because they make both execution and review easier. The more repeatable patterns the project defines, the less an agent has to invent while working and the easier it is for a reviewer to verify whether the generated work followed the intended model.

## What AI Divergence Includes

AI divergence can include:

- Invented files, APIs, commands, dependencies, requirements, or test results.
- Misstated behavior of existing code or external libraries.
- Assumptions presented as verified facts.
- Implementation that drifts from approved architecture or logic patterns.
- Work that expands beyond the agreed scope.
- Code that passes syntax checks but fails the intended behavior.
- Tests that confirm only superficial behavior or encode incorrect expectations.
- Explanations that sound reasonable but are not grounded in repository evidence.
- Changes that satisfy the prompt while violating maintainability, security, or reviewability expectations.

## Workflow Mitigations

This workflow mitigates AI divergence through repeatable engineering controls:

- Architecture-first planning establishes the intended shape of the solution before code is written.
- Work breakdown artifacts define scope, sequence, assumptions, and acceptance expectations.
- Pattern documentation gives agents explicit architecture, design, syntax, logic, and test models to follow.
- Scoped implementation keeps changes reviewable and limits unintended behavior.
- Agent self-checks require comparison against the agreed plan, architecture, and patterns.
- Human review validates intent, correctness, maintainability, and pattern conformance.
- Independent review by another agent can challenge assumptions and identify missed divergence.
- Formatting and style standards make code easier to inspect.
- Unit, smoke, regression, integration, and golden-output tests provide evidence that behavior changed as intended.
- Durable Markdown artifacts preserve context outside a single chat thread and reduce session drift.

These controls do not assume the AI will always be correct. They assume AI may diverge and require evidence before trust is granted.

## Verification Expectations

Agents should clearly separate verified facts from assumptions.

Before implementation, an agent should be able to state what it verified and what it is assuming. Verification may come from reading repository files, running commands, inspecting test output, checking project documentation, or consulting authoritative external documentation when current external behavior matters.

If a claim cannot be verified and the claim is important to correctness, scope, safety, security, or architecture, it should be treated as a blocker until resolved.

Agents should also use local documentation as part of verification. Rules, constraints, AGENT instructions, architecture notes, pattern documents, work artifacts, and test strategy documents help the agent infer the intended way to work without relying on chat memory or broad training assumptions.

## Pattern Expectations

Patterns are one of the main controls against AI divergence.

Architecture patterns describe the shape and boundaries of the system. Design and logic patterns describe how behavior should be expressed. Syntax and formatting patterns make the implementation easier to compare across files. Test patterns describe how correctness should be demonstrated.

Agents should follow documented patterns unless the work explicitly requires a change to the pattern. Reviewers should treat pattern conformance as a first-class review criterion, not as a style preference. When work intentionally changes or introduces a pattern, that change should be documented so future agents and reviewers can use it consistently.

## Testing Expectations

Tests exist to provide confidence in agent execution.

The implementor should understand what each relevant test proves, what it does not prove, and whether the expected result is accurate. Passing tests are useful only when the tests encode the intended behavior.

Deterministic code is easier to verify. Known inputs, known outputs, fixtures, and golden copies make it possible to compare agent-generated behavior against trusted results. Unit, smoke, regression, integration, and golden-output tests should be used where appropriate to create evidence that the implementation is correct and repeatable.

Code validation should include both automated checks and human judgment about whether the checks are meaningful for the change being made.

## Review Expectations

Review should check more than whether the code compiles or the requested text was added. Review should ask whether the work:

- Matches the agreed scope and work breakdown.
- Follows the documented architecture and logic patterns.
- Follows established design, syntax, formatting, and test patterns.
- Uses real repository APIs, files, and dependencies.
- Preserves intended behavior outside the change area.
- Includes appropriate tests, golden outputs, or validation evidence.
- Uses deterministic behavior where deterministic behavior is required for validation.
- Is formatted and structured so future reviewers can reason about it.
- Clearly identifies any remaining assumptions or risks.

## Stop Conditions

An agent should stop and ask for direction when:

- A critical assumption cannot be verified.
- The requested change conflicts with the documented architecture or patterns.
- Required files, dependencies, commands, or test environments are unavailable.
- The scope expands beyond the approved work artifact.
- The agent cannot distinguish between a repository fact and an inference.
- Continuing would require guessing about user intent, safety, security, or correctness.

Stopping is not a failure of the workflow. It is one of the controls that prevents unverified assumptions from becoming accepted work.

## Relationship to the Process

This document explains the reason behind the workflow controls. Detailed operating instructions remain in the process documents, architecture artifacts, pattern documents, work breakdown structures, coding standards, review practices, and test strategy.

The central idea is simple: trust is earned through evidence, not generated by AI confidence.
