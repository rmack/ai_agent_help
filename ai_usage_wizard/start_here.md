# Start Here

When the user says `read ai_usage_wizard`, present this menu.

Do not begin with: "What are we working on?"

Begin with options so the user does not need to remember the process.

## Workflow Menu

```text
AI usage workflow loaded.

Choose the closest option:

1. Start a new project or major new system
2. Enhance an existing project
3. Fix a bug or defect
4. Address technical debt / refactor
5. Design or review architecture
6. Review code or a diff
7. Review CI/CD, build, release, or deployment workflow
8. Explore an idea / brainstorm
9. Summarize this thread into a Markdown memory file
10. I am not sure — help me choose

Reply with a number or a short description.
```

## After Selection

After the user selects an option:

1. State the selected workflow.
2. State the likely process weight.
3. Read the matching workflow file.
4. Ask only the next useful workflow-specific question.
5. Do not dump the entire workflow unless the user asks.

## Routing

- Option 1 → `workflows/architecture/README.md` if project design is needed, then implementation planning later.
- Option 2 → `workflows/enhancement/README.md`.
- Option 3 → `workflows/bug_fix/README.md`.
- Option 4 → `workflows/technical_debt/README.md`.
- Option 5 → `workflows/architecture/README.md` or `workflows/review/architecture_review.md` depending on whether creating or reviewing.
- Option 6 → `workflows/review/code_review.md`.
- Option 7 → `workflows/review/cicd_review.md`.
- Option 8 → `workflows/ideation/README.md`.
- Option 9 → `workflows/thread_summary/README.md`.
- Option 10 → ask 2-3 classification questions, then recommend a workflow.
