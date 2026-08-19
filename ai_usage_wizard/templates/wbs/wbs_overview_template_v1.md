# WBS Overview v1 Template

> **Template maturity:** Provisional. Repository hierarchy, status rollup, and external
> tasking synchronization vary by organization. Review and customize this template
> before adopting it as a repository's authoritative work inventory.

## Purpose

[Repository-wide work inventory and external-tasking traceability purpose.]

## Scope and Boundaries

This overview records:

- [Streams, independently tracked Work Packages, and milestones.]
- [Repository identifiers and parent relationships.]
- [Links to documents that define the work.]
- [Stable external task references.]
- [Concise status, dependency, owner, and blocker information.]

This overview does not own:

- Detailed technical scope or implementation instructions.
- Package acceptance criteria or validation evidence.
- External dates, duration, notifications, or percent-complete values.
- As-built behavior, which remains authoritative in repository evidence.

## How to Read This Overview

| Field | Meaning |
| --- | --- |
| WBS ID | Repository work identifier. |
| Parent | Parent Stream or higher-level identifier. |
| Type | Stream, Work Package, Task, or Milestone. |
| Title | Concise work name. |
| Status | Not Started, In Progress, Blocked, Complete, or Superseded. |
| Owner | Assigned owner, when known. |
| Depends On | Work that must precede this item. |
| Definition Document | Stream or Work Package that defines the work. |
| External Xref | Stable external task ID or URL. |
| Notes | Concise blockers, discrepancies, or evidence. |

## Status Rules

- **Not Started:** No work has begun.
- **In Progress:** Work is underway or partially complete.
- **Blocked:** Progress requires a named dependency, decision, or input.
- **Complete:** Required outcomes are supported by acceptance, review, and validation
  evidence.
- **Superseded:** Another identified item or document replaced this one.

## Work Inventory

| WBS ID | Parent | Type | Title | Status | Owner | Depends On | Definition Document | External Xref | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [1] | — | Stream | [Example stream] | Not Started | TBD | — | `[path]` | TBD | [Note] |
| [1.1] | [1] | Work Package | [Example package] | Not Started | TBD | — | `[path]` | TBD | [Note] |

## Known Reconciliation Items

- [External/repository discrepancy and evidence needed to reconcile it.]

## Open Overview Design Decisions

- Required columns and hierarchy representation.
- Stream and milestone status-rollup rules.
- External task identity and synchronization conventions.
- Whether independently scheduled tasks appear here or become Work Packages.
