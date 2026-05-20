# AI Usage Documentation

This directory contains organization-facing documentation for adopting and governing AI use in software development.

The current documents focus on responsible AI usage, developer operating practices, and practical controls for keeping AI-assisted engineering work understandable, reviewable, secure, and aligned with organizational expectations.

## Organizational AI Adoption Overview

When introducing AI into an organization, the documentation should be part of a broader operating model. The table below outlines the core components to consider.

| Category | Component | Description |
| --- | --- | --- |
| Strategy | Outcomes/KPIs | Business goals, success metrics, target use cases. |
| Risk | Risk & Compliance | Classification, approvals, audit expectations. |
| Documentation | Policy | What must be true: stable, enforceable requirements. |
| Documentation | Standards | Concrete rules applied to code: non-negotiable expectations. |
| Documentation | Guidance | How to follow policy and standards: adaptable recommendations. |
| Documentation | Playbook | How individuals think and operate: practical execution. |
| Enforcement | Governance | Who enforces expectations and approves exceptions. |
| Enforcement | Controls | Automated enforcement such as CI, linting, scanning, logging, and review gates. |
| Operations | Cost / FinOps | Usage accountability, budgets, monitoring, and cost controls. |
| Operations | Tooling Strategy | Approved tools, data boundaries, access models, and integration expectations. |
| Organization | Enablement | Training, onboarding, examples, and support channels. |
| Organization | Feedback Loop | Continuous improvement based on usage, incidents, developer feedback, and tool changes. |
| Organization | Ownership | Clear responsibility across engineering, security, legal, compliance, finance, and leadership. |

## Documents Available Today

| Document | Format | Purpose |
| --- | --- | --- |
| `AI_Usage_Policy.md` | Markdown source | Defines mandatory requirements for responsible and secure AI use in software development. |
| `docx/AI Usage Policy.docx` | Word export | Shareable version of the AI usage policy. |
| `AI_Usage_Guidance.md` | Markdown source | Provides practical guidance for applying the policy during AI-assisted development. |
| `docx/AI Usage Guidance.docx` | Word export | Shareable version of the AI usage guidance. |
| `Engineering_Playbook_for_AI_Usage.md` | Markdown source | Defines how engineers should use AI tools while preserving quality, architecture, validation, and control. |
| `docx/Engineering Playbook for AI Usage.docx` | Word export | Shareable version of the full engineering playbook. |
| `Engineering_Playbook_for_AI_Usage_Quick_Reference.md` | Markdown source | Lightweight reference for day-to-day engineering use. |
| `docx/Engineering Playbook for AI Usage - Quick Reference.docx` | Word export | Shareable version of the quick reference. |

## How These Documents Fit Together

| Document Type | Role |
| --- | --- |
| Policy | Defines mandatory requirements and boundaries. |
| Guidance | Explains how to apply policy in practical development situations. |
| Playbook | Describes how engineers should think, prompt, review, validate, and operate with AI. |
| Quick Reference | Gives developers a compact checklist for daily use. |


## Suggested Next Additions

The current docs cover policy, guidance, and engineering playbook material. Likely next additions are:

- AI usage standards for code, data, security, and architecture
- approved tooling and data boundary matrix
- governance and exception process
- cost monitoring and FinOps model
- onboarding and training path
- audit evidence and compliance checklist
- feedback and continuous improvement process
