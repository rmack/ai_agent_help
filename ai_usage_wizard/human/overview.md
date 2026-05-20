# Human Overview

This process helps developers use AI without giving up engineering judgment.

## Core Principle

The developer drives the work. AI assists, accelerates, challenges, summarizes, implements, and reviews, but it does not own requirements, architecture, correctness, or final decisions.

## Why This Exists

AI can produce code quickly. Without a process, that can lead to:

- architecture drift
- inconsistent patterns
- larger diffs
- shallow validation
- code the developer does not fully understand
- useful decisions trapped in chat history

The process exists to keep AI useful, constrained, and reviewable.

## Architecture-First Model

For design-heavy work, move through:

```text
CONOPS
→ Conceptual Architecture
→ Logical Architecture
→ Physical Architecture
→ Implementation Plan
```

Do not jump to files or code before the operating model and architecture are understood.

## Workflow Modes

The process changes based on intent:

- New Project / Architecture Design
- Existing Project Enhancement
- Bug Fix
- Technical Debt / Refactor
- Architecture Review
- Code Review
- CI/CD Review
- Ideation / Brainstorming
- Thread Summary / Memory Capture

## Phase-Based Execution

For multi-phase workflows, the agent should not blindly continue. It should complete one phase, summarize results, and ask whether to revise or continue.

## Durable Memory

Threads are temporary. Important knowledge should be captured in Markdown files, documentation, tests, architecture notes, `AGENTS.md`, or future-thread summaries.

## Validation

Validation should distinguish:

- unit tests — isolated logic correctness
- smoke tests — system/workflow runs
- regression tests — unintended behavior changes
- manual review — human understanding and acceptance

Passing tests do not automatically prove correctness.
