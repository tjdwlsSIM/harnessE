
---

# 14. `prompts/apply-to-project.md`

```md
# Apply harnessE to Project

Use this prompt when applying harnessE to an existing project.

## Prompt

Apply the harnessE structure to this project.

Before editing:

1. Read `AGENTS.md` if it exists.
2. Inspect the current project structure.
3. Identify the framework and main folders.
4. Do not modify existing feature code.

Your task:

1. Create or update `AGENTS.md`.
2. Create a `docs/` folder.
3. Create a `rules/` folder.
4. Create a `tasks/` folder.
5. Add project-specific documentation.
6. Summarize the current architecture.
7. Add AI agent rules for future development.

Required files:

```txt
AGENTS.md
docs/project-context.md
docs/architecture.md
docs/coding-convention.md
docs/checklist.md
docs/workflow.md
rules/ai-agent-rules.md
rules/frontend-rules.md
rules/backend-rules.md
rules/git-rules.md
tasks/task-template.md