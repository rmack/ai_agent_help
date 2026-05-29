# Checklists

## Architecture / New Project

- Complete CONOPS.
- Confirm or revise CONOPS.
- Complete conceptual architecture.
- Confirm or revise conceptual architecture.
- Complete logical architecture.
- Confirm or revise logical architecture.
- Complete physical architecture.
- Confirm implementation approach.
- Identify validation expectations.
- Capture architecture decision summary.

## Enhancement

- Define requested behavior.
- Inspect current architecture.
- Identify existing patterns.
- Confirm affected files/modules.
- Confirm constraints and non-goals.
- Propose minimal plan.
- Implement in small slices.
- Validate behavior.
- Update docs or patterns if needed.

## Bug Fix

- Define observed behavior.
- Define expected behavior.
- Reproduce or characterize the issue.
- Identify likely code path.
- Identify root cause.
- Add or identify failing test.
- Make smallest safe fix.
- Run targeted validation.
- Run regression validation if needed.
- Document root cause.

## Technical Debt

- Define the debt.
- Confirm behavior should not change.
- Identify current behavior to preserve.
- Identify refactor boundary.
- Add characterization tests if needed.
- Refactor in small steps.
- Validate no behavior change.
- Capture improved pattern.

## Review

- Define review scope.
- Identify review focus.
- Separate blocking, should-fix, and optional findings.
- Identify validation gaps.
- Check whether the implementation follows the original handoff, repo logic,
  code patterns, and project instructions.
- Compare agent review findings with the developer's own review.
- Send valid findings back to the implementation agent for evaluation and fixes.
- Re-review after fixes, using a secondary agent review for non-trivial or high-risk changes.
- Recommend next actions.

## Correctness Evidence

- Review unit tests for meaningful assertions and edge cases.
- Run relevant unit tests.
- Run smoke tests for changed workflows or execution blocks.
- Confirm smoke tests fail loudly when development-time assumptions are broken.
- Run regression checks when behavior stability matters.
- Compare golden artifacts when deterministic outputs or generated files change.
- Review golden artifact diffs before accepting regenerated outputs.
- Complete human code review.
- Complete agent code review for non-trivial AI-generated changes.
- Record what validation proved and what it did not prove.

## Thread Summary

- Capture purpose.
- Capture major topics.
- Capture decisions.
- Capture open questions.
- Capture future thread seeds.
- Capture reusable prompts or patterns.
