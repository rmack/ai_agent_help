# WBS Templates

## Purpose

These templates turn approved development planning into durable, repository-based work
artifacts that humans and AI agents can both understand, execute, review, and close.
They support the AI Usage workflows; they do not replace workflow selection, phase
gates, human approval, repository instructions, or validation.

## Artifact Model

```text
WBS Overview
  ├── WBS Stream
  │     ├── WBS Work Package
  │     │     └── Task 1..n
  │     └── WBS Work Package
  │           └── Task 1..n
  └── WBS Work Package
        └── Task 1..n
```

- The **WBS Overview** is a repository-wide work inventory and cross-reference to an
  external tasking or scheduling system. Its v1 template is provisional.
- A **WBS Stream** coordinates a larger objective made of multiple related Work
  Packages. It records sequencing, dependencies, shared decisions, and status.
- A **WBS Work Package** defines one bounded, reviewable outcome containing 1..n tasks.
  Its type may be design, investigation, implementation, validation, documentation, or
  a clearly justified combination.

A small change normally needs only one Work Package. Do not create a Stream merely to
hold one package. Topic indexes and supporting documents are optional.

## Supporting Documents

CONOPS, conceptual/logical/physical architecture, decision records, findings, research,
open-item registers, and validation reports remain supporting documents. They explain
the problem, architecture, decisions, or evidence. They do not authorize every action
they describe.

```text
Supporting documents explain the system and evidence.
Streams organize related Work Packages.
Work Packages define bounded work and its completion evidence.
```

## When to Create WBS Artifacts

First select and follow the appropriate AI Usage workflow and process weight. Create a
Work Package after the workflow has produced enough approved scope, constraints,
acceptance criteria, validation expectations, and stop conditions to define executable
work. Create a Stream when multiple packages combine into a larger outcome.

Typical workflow use:

| Workflow | WBS use |
| --- | --- |
| Architecture/new system | Supporting architecture documents, then a Stream and bounded design/implementation packages when needed |
| Enhancement | Usually one Work Package after pattern discovery and design-impact approval |
| Bug fix | Usually one Work Package after reproduction and root-cause analysis |
| Technical debt | Usually one Work Package after characterization and refactor-boundary approval |
| Review | Findings may propose follow-up packages; review does not authorize their execution |
| Ideation | No WBS until an idea is selected and moved into a development workflow |
| Thread summary | Durable memory, not automatically a WBS |

## How to Use the Templates

1. Read repository instructions and select the correct AI Usage workflow.
2. Copy the appropriate template into the target repository's work-document area.
3. Use repository naming and identifier conventions; do not assume a `WBS/` directory
   exists unless the repository defines one.
4. Replace bracketed placeholders and follow the embedded HTML comments.
5. Remove optional sections that add no useful information; avoid `N/A` filler.
6. Customize generic impact fields for important local contracts and risks.
7. Verify claims, paths, prerequisites, architecture, and validation commands against
   the current repository.
8. Obtain human execution approval before implementation.
9. Give the Work Package to the implementation agent and require it to explain its
   understanding, approach, risks, validation plan, and stop conditions before editing.
10. Execute tasks in small steps, update checkboxes without changing scope silently,
    and stop when approval or design is insufficient.
11. Complete the Closeout Record with actual changes, validation evidence, review,
    limitations, and follow-up work.

Copying examples:

```text
ai_usage_wizard/templates/wbs/wbs_stream_template_v1.md
  -> <repository work area>/wbs_stream_<topic>_v1.md

ai_usage_wizard/templates/wbs/wbs_template_v1.md
  -> <repository work area>/wbs_<work_package>_v1.md
```

The generic templates are starting points. A repository owns its customized copies and
may add domain-specific contract checks while preserving the core intent.

## Controls

Keep these concepts distinct:

- **Process weight:** Lightweight, Standard, or Heavyweight; scales process depth.
- **Work type:** The kind of outcome being produced.
- **Work status:** Not Started, In Progress, Blocked, Complete, or Superseded.
- **Execution approval:** Human authorization to begin the package; Pending is not
  authorization.

A Work Package Scope is the execution boundary. Referenced documents provide context,
not broader authorization. Material changes to scope, architecture, contracts,
dependencies, security, data handling, or validation require a stop, document revision,
and renewed human approval.

Task checkboxes show completed and remaining tasks. They are not percent-complete
values and do not replace acceptance criteria, review, validation, or closeout evidence.

## Sources of Truth

| Information | Authority |
| --- | --- |
| Workflow and phase gates | AI Usage process and selected workflow |
| Repository execution rules | Applicable repository instruction files |
| Current behavior | Repository code, contracts, runtime evidence, and authoritative docs |
| Stream composition | WBS Stream |
| Package scope and acceptance | Approved WBS Work Package |
| Schedule, dates, and assignments | External tasking tool, when used |
| Technical completion | Acceptance criteria, review, validation, and Closeout Record |

The developer remains the architect, reviewer, and decision-maker. AI-generated WBS
content is provisional until verified and approved.

