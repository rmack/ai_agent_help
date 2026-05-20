# Process Weights

Use process weight to scale the workflow to the risk.

## Lightweight

Use for small, low-risk, localized work.

Characteristics:

- few files
- clear scope
- low risk
- no architecture change
- no data/security/dependency impact

Minimum flow:

```text
Intent → Scope → Small Plan → Change/Review → Validate → Done
```

## Standard

Use for normal development tasks.

Characteristics:

- moderate uncertainty
- existing project change
- patterns need to be checked
- tests need to be run or added

Minimum flow:

```text
Intent → Pattern Review → Plan → Small Execution → Validation → Closeout
```

## Heavyweight

Use for architecture, high-risk, broad, or security-sensitive work.

Characteristics:

- new system or major design
- cross-module changes
- CI/CD/deployment impact
- sensitive data
- authentication/authorization
- new dependencies
- unclear requirements

Minimum flow:

```text
CONOPS → Conceptual → Logical → Physical → Risk Gates → Plan → Validation → Documentation
```
