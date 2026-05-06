# AGENTS.md

## Purpose

This repository follows the `harnessE` harness engineering standard.

`harnessE` is a reusable AI-assisted development standard that helps AI coding agents work safely, consistently, and predictably across different projects.

This file is the main instruction document for AI agents such as Codex, Claude Code, Cursor, Copilot, and other AI coding tools.

---

## Core Principle

AI agents must act as careful software engineers, not automatic code generators.

Before modifying any code, the AI agent must understand:

1. The project purpose
2. The current folder structure
3. The related source files
4. The user’s task
5. The existing coding style
6. The harnessE rules

The agent must prioritize safe, small, and reviewable changes.

---

## Required Reading Order

Before starting any task, the AI agent must read these files in order if they exist:

1. `README.md`
2. `prompts/base-prompt.md`
3. `docs/project-context.md`
4. `docs/architecture.md`
5. `docs/coding-convention.md`
6. `docs/workflow.md`
7. `docs/checklist.md`
8. `rules/ai-agent-rules.md`
9. `rules/frontend-rules.md`
10. `rules/backend-rules.md`
11. `rules/git-rules.md`

The AI agent should not edit code before understanding these documents.

---

## Main Workflow

Every AI-assisted development task must follow this flow:

```txt
Request
→ Context Check
→ File Inspection
→ Plan
→ Implementation
→ Review
→ Final Summary
```

---

## Before Editing

Before making changes, the AI agent should:

1. Inspect the project structure.
2. Find related files.
3. Identify existing patterns.
4. Explain the intended change briefly.
5. Modify only the necessary files.

For most tasks, the agent should explain:

```txt
I will inspect these files:
- file 1
- file 2
- file 3

I expect to modify:
- file 1: reason
- file 2: reason
```

For very small changes, this can be brief.

---

## Implementation Rules

When editing a project, the AI agent must follow these rules:

- Modify only files related to the task.
- Do not rewrite unrelated files.
- Do not delete existing files unless explicitly requested.
- Do not rename major folders unless explicitly requested.
- Preserve existing behavior unless the task requires a behavior change.
- Prefer existing project patterns over new patterns.
- Keep changes small and reviewable.
- Keep UI, logic, API calls, and utility functions separated.
- Do not add unnecessary dependencies.
- Do not expose secrets, tokens, API keys, or private environment values.
- Do not hard-code local or production URLs.
- Follow the existing naming and formatting style.

---

## Frontend Rules

For frontend projects, follow these principles:

- Use functional components.
- Keep components focused and reusable.
- Move repeated UI into reusable components.
- Keep page files focused on layout and composition.
- Keep API calls inside `services/`.
- Keep reusable logic inside `hooks/` or `utils/`.
- Use environment variables for API base URLs.
- Handle loading, error, empty, and success states when needed.
- Keep class names readable.
- Do not break existing responsive behavior.

Recommended structure:

```txt
src/
├─ app/
├─ pages/
├─ components/
├─ features/
├─ hooks/
├─ services/
├─ utils/
├─ assets/
└─ styles/
```

---

## Backend Rules

For backend projects, follow these principles:

- Keep routes, controllers, services, models, middlewares, and utilities separated.
- Validate request body, params, and query values.
- Return consistent success and error responses.
- Store sensitive values in environment variables.
- Do not expose internal error details to users.
- Do not trust frontend input blindly.
- Keep business logic out of route files when possible.

Recommended structure:

```txt
src/
├─ routes/
├─ controllers/
├─ services/
├─ models/
├─ middlewares/
├─ utils/
└─ config/
```

---

## Git Rules

The AI agent must not commit changes automatically unless the user explicitly requests it.

Before suggesting a commit, check:

- No unrelated files are included.
- No `.env` files are included.
- No secrets are included.
- No unnecessary generated files are included.
- The change can be explained clearly.

Recommended commit format:

```txt
type: short description
```

Examples:

```txt
feat: add memory upload form
fix: resolve login redirect issue
docs: update harness engineering guide
refactor: separate API services from components
```

---

## Forbidden Actions

The AI agent must not:

- Rewrite the entire project without permission.
- Modify unrelated files.
- Delete existing files without permission.
- Rename major folders without permission.
- Add unnecessary packages.
- Commit `.env` files.
- Expose API keys or secrets.
- Hard-code local or production URLs.
- Ignore existing code style.
- Skip the final summary.
- Make large guesses without inspecting the repository.

---

## When Context Is Missing

If important context is missing, the AI agent should:

1. Inspect the repository first.
2. Look for existing patterns.
3. Make the safest reasonable assumption.
4. Ask a focused question only if the task cannot be completed safely.

The agent should not make large structural changes based on assumptions.

---

## Required Final Response Format

After completing a task, the AI agent must respond with:

```txt
Summary:
- Briefly explain what was done.

Changed files:
- file 1: what changed
- file 2: what changed

Important details:
- Mention important implementation choices.

How to test:
- Step 1
- Step 2
- Step 3

Risks or follow-up:
- Mention anything that should be checked later.
```

---

## harnessE Priority Rule

When making decisions, follow this priority order:

```txt
safe change > fast change
small edit > large rewrite
existing pattern > new pattern
clear code > clever code
human reviewability > automatic completion
```

---

## Source of Truth

This file is the entry point for AI agents.

Detailed rules are defined in:

- `prompts/base-prompt.md`
- `docs/project-context.md`
- `docs/architecture.md`
- `docs/coding-convention.md`
- `docs/workflow.md`
- `docs/checklist.md`
- `rules/ai-agent-rules.md`
- `rules/frontend-rules.md`
- `rules/backend-rules.md`
- `rules/git-rules.md`

AI agents must follow these documents when working on this project.

---

## Codex Slash-Style Commands

This project uses slash-style command templates for Codex.

These commands are not dependent on a specific AI vendor feature.  
If the user starts a request with one of the commands below, Codex must interpret it as an instruction to read the matching file in `commands/`.

## Available Commands

```txt
/apply-harness
/feature
/refactor
/review
/fix
/gpush
```

## Command Mapping

When the user types:

```txt
/apply-harness
```

Codex must read and follow:

```txt
commands/apply-harness.md
```

When the user types:

```txt
/feature [request]
```

Codex must read and follow:

```txt
commands/feature.md
```

The text after `/feature` is the feature request.

When the user types:

```txt
/refactor [request]
```

Codex must read and follow:

```txt
commands/refactor.md
```

The text after `/refactor` is the refactor request.

When the user types:

```txt
/review [target]
```

Codex must read and follow:

```txt
commands/review.md
```

The text after `/review` is the review target.

When the user types:

```txt
/fix [bug description]
```

Codex must read and follow:

```txt
commands/fix.md
```

The text after `/fix` is the bug description.

## Codex Command Rule

Codex must treat slash-style commands as shortcuts for longer prompts.

Example:

```txt
/feature 사진 업로드 후 미리보기 기능을 추가해줘
```

Means:

```txt
Read commands/feature.md.
Use "사진 업로드 후 미리보기 기능을 추가해줘" as the feature request.
Follow the harnessE standard.
```

## If Slash Commands Are Not Recognized

If the Codex environment does not support custom slash commands directly, the user can write:

```txt
commands/feature.md 기준으로 작업해줘.

요청:
사진 업로드 후 미리보기 기능을 추가해줘.
```

Codex must treat this the same as:

```txt
/feature 사진 업로드 후 미리보기 기능을 추가해줘
```


그리고 아래 내용도 추가해.

````md
## Git Push Command

When the user types:

```txt
/gpush [commit message]

Codex must read and follow:
commands/gpush.md

The text after /gpush is the commit message.

Example:
/gpush docs: update harnessE guide

Means:
git status --short
git add .
git status --short
git commit -m "docs: update harnessE guide"
git push

Using /gpush is explicit permission to run the Git add, commit, and push flow.

However, Codex must stop before committing if sensitive files such as .env, .env.local, or node_modules/ are staged.