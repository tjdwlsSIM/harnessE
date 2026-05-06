
---

## 5. `prompts/apply-to-project.md`에 넣을 프롬프트

이 파일이 실제로 가장 자주 쓰일 거야.

```md
# Apply harnessE to a Project

Use this prompt when applying the harnessE structure to an existing project.

## Prompt

You are working inside an existing software project.

Apply the harness engineering structure from the `harnessE` repository.

Before editing:

1. Read `AGENTS.md`.
2. Inspect the current project folder structure.
3. Identify the frontend, backend, routes, components, services, and config files.
4. Do not modify existing feature code unless necessary.

Your task:

1. Create or update `AGENTS.md`.
2. Create a `docs/` folder if it does not exist.
3. Add:
   - `docs/project-context.md`
   - `docs/architecture.md`
   - `docs/coding-convention.md`
   - `docs/checklist.md`
   - `docs/workflow.md`
4. Create a `rules/` folder if it does not exist.
5. Add:
   - `rules/frontend-rules.md`
   - `rules/backend-rules.md`
   - `rules/git-rules.md`
   - `rules/ai-agent-rules.md`
6. Create a `tasks/task-template.md` file.
7. Summarize the current project structure in `docs/architecture.md`.
8. Write future AI instructions in `AGENTS.md`.

Constraints:

- Do not change unrelated source code.
- Do not delete existing files.
- Do not rename existing folders unless explicitly requested.
- Keep the structure compatible with Codex, Claude Code, Cursor, and Copilot.

After finishing, provide:

- Summary
- Created files
- Modified files
- How to use this harness in future AI sessions