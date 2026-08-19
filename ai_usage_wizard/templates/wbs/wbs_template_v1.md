# WBS [WBS ID] — [Work Package Title]

<!--
Use this template for one bounded, reviewable outcome containing 1..n tasks. Remove
optional sections that do not add useful information.
-->

## Document Control

| Field | Value |
| --- | --- |
| WBS ID | [Repository identifier] |
| Work type | [Design / Investigation / Implementation / Validation / Documentation / Mixed] |
| Process weight | [Lightweight / Standard / Heavyweight] |
| Status | Not Started |
| Execution approval | [Pending / Approved by name on YYYY-MM-DD] |
| Owner | TBD |
| Parent Stream | [Stream ID and link, or None] |
| Overview reference | [Overview reference or TBD] |
| External task | [Stable URL, ID, or TBD] |
| Version | v1 |
| Updated | [YYYY-MM-DD] |
| Depends on | [WBS IDs or None] |
| Blocks | [WBS IDs or None] |

## Purpose

[Why this Work Package exists.]

## Goal

[One concrete, testable outcome.]

## Background and Current State

<!-- Required. Summarize verified facts and link to detailed supporting documents. -->

[Verified as-built behavior, prior decisions, and the problem being addressed.]

## Supporting Documents

<!-- Optional: include only material required to understand or execute this package. -->

| Document | Relevance |
| --- | --- |
| `[path]` | [Why the executor must read it] |

## Scope

### In Scope

- [Required work or outcome.]

### Out of Scope

- [Explicitly excluded adjacent work.]

## Requirements

- [Required behavior or output.]

## Constraints and Invariants

- [Behavior, architecture, security, dependency, determinism, or compatibility rule.]

## Risks

<!-- Optional: foreseeable ways the approach could fail or drift while in scope. -->

- [Risk and potential impact.]

## Dependencies, Blockers, and Decisions

### Prerequisites

- [Required package, artifact, decision, or None.]

### Current Blockers

- None.

### Decisions Required

- None.

## Contract and Artifact Impact

<!-- Required. TBD is acceptable when the pending decision is named. -->

| Area | Expected Impact |
| --- | --- |
| Schemas and serialized formats | [None, TBD, or describe] |
| Configuration and extension contracts | [None, TBD, or describe] |
| Generated or golden artifacts | [None, TBD, or describe] |
| External interfaces | [None, TBD, or describe] |
| Security and data handling | [Unaffected, TBD, or describe] |
| Dependencies | [None, TBD, or describe] |
| Deterministic behavior | [Unaffected, TBD, or describe] |

## Relevant Architecture and Existing Patterns

<!-- Optional. Use verified repository paths and patterns; do not guess. -->

- `[path]` — [Relevant architecture, implementation, or test pattern.]

## Expected Behavior

<!-- Optional when Acceptance Criteria already captures these cases sufficiently. -->

### Success Cases

- [Observable successful behavior.]

### Failure and Validation Behavior

- [Invalid state and expected fail-loud behavior.]

### Compatibility Expectations

- [Existing behavior or interface that must remain unchanged.]

## Likely Files and Areas

<!-- Optional planning expectations; verify them before editing. -->

### Expected to Change

- `[path]` — [Reason]

### Expected Not to Change

- `[path or area]` — [Boundary reason]

## Tasks

- [ ] 1. [Task with an observable output.]
- [ ] 2. [Task with an observable output.]
- [ ] 3. [Task with an observable output.]

## Implementation Guidance

<!-- Optional recommendations, distinct from mandatory requirements. -->

- [Suggested approach, existing helper, or implementation sequence.]

## Acceptance Criteria

- [Observable pass/fail criterion.]

## Validation Plan

| Check | Command or Method | What It Proves | Limitations |
| --- | --- | --- | --- |
| Unit | `[command]` | [Evidence] | [What remains unproven] |
| Integration/smoke | `[command]` | [Evidence] | [What remains unproven] |
| Regression/golden | `[command or comparison]` | [Evidence] | [What remains unproven] |
| Conditional | [Contract/security/performance/migration/manual check] | [Evidence] | [What remains unproven] |
| Human review | [Diff/artifact review] | [Evidence] | [What remains unproven] |
| Agent review | [Review scope] | [Evidence] | [What remains unproven] |

## Stop Conditions

Stop and request human direction if:

- Execution approval is Pending.
- A critical repository or architecture assumption cannot be verified.
- Required work expands beyond this Scope.
- A contract, dependency, security, data-handling, or external-interface change is
  required but not approved here.
- [Package-specific stop condition.]

## Definition of Done

- The Goal and Acceptance Criteria are satisfied.
- The final work remains within the approved Scope.
- Required review and validation are complete and their limits are understood.
- Contract, artifact, security, dependency, determinism, and compatibility impacts are
  recorded accurately.
- Relevant documentation is reviewed and updated as needed.
- Remaining risks and follow-up work are recorded.
- The Closeout Record below is completed.

---

## Closeout Record

<!-- Complete during closeout; do not pre-populate results. -->

### Final Status

[Complete / Blocked / Superseded]

### Work Completed

- [Completed task and outcome.]

### Files Changed

- `[path]` — [Purpose]

### Behavior and Contract Impact

| Question | Answer |
| --- | --- |
| Behavior changed? | [Yes/No — explanation] |
| Schema or serialized format changed? | [Yes/No — explanation] |
| External contract changed? | [Yes/No — explanation] |
| Security or data handling changed? | [Yes/No — explanation] |
| Dependencies changed? | [Yes/No — explanation] |
| Deterministic behavior affected? | [Yes/No — explanation] |

### Validation Performed

- `[Command or check]`
  - Proves: [What it proves]
  - Does not prove: [Known limitation]

### Review Performed

- Human review: [Summary or pending]
- Independent agent review: [Summary, reason skipped, or pending]

### Documentation Review

- [Document reviewed, whether it changed, and why.]

### Remaining Risks and Follow-Up Work

- [Risk, limitation, or linked follow-up package.]

