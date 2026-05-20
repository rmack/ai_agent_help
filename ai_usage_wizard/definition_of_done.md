# Definition of Done

A task is done only when the developer can understand, review, validate, and preserve the work.

## Checklist

### Goal and Scope

- The original goal is satisfied.
- The final scope matches the approved scope.
- Scope changes were explicitly approved.

### Architecture and Patterns

- Existing architecture was preserved or intentionally changed.
- Existing patterns were followed or a new pattern was approved.
- No unnecessary abstraction was introduced.
- Existing bad code was not treated as precedent.

### Review

- The developer reviewed the meaningful changes.
- The diff is small enough to review.
- Risks and tradeoffs are understood.

### Validation

- Relevant unit tests were run.
- Smoke tests were run if workflow execution changed.
- Regression tests were run if deterministic behavior or outputs changed.
- Manual validation was performed where needed.
- Validation limits are known.

### Risk Controls

- Security review was performed if relevant.
- No unauthorized dependency was added.
- No secrets or sensitive data were exposed.
- Data handling and licensing concerns were considered.

### Documentation

- Durable decisions were captured.
- Architecture or pattern docs were updated if needed.
- Thread summary was created if reusable context was produced.

### Final State

- Known limitations are documented.
- Follow-up tasks are captured.
- The work is ready for commit, PR, handoff, or continued discussion.
