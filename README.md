# harnessE

`harnessE` is a reusable harness engineering standard for AI-assisted software development.

It helps AI coding agents such as Codex, Claude Code, Cursor, Copilot, and other tools work with the same rules, structure, and workflow across different projects.

---

## Purpose

The purpose of `harnessE` is to make AI-assisted development safer and more consistent.

Instead of giving every AI tool different instructions every time, this repository provides a shared standard that defines:

- How AI agents should understand a project
- How AI agents should inspect files before editing
- How project architecture should be documented
- How frontend and backend code should be separated
- How tasks should be described
- How final summaries should be written
- What AI agents should avoid

---

## Main Idea

`harnessE` is not just a prompt collection.

It is a reusable development standard for AI coding workflows.

The main principle is:

```txt
AI should understand the project before changing the project.
```

---

## Repository Structure

```txt
harnessE/
├─ AGENTS.md
├─ README.md
├─ docs/
│  ├─ project-context.md
│  ├─ architecture.md
│  ├─ coding-convention.md
│  ├─ workflow.md
│  └─ checklist.md
├─ prompts/
│  ├─ base-prompt.md
│  ├─ apply-to-project.md
│  ├─ feature-prompt.md
│  ├─ refactor-prompt.md
│  └─ review-prompt.md
├─ rules/
│  ├─ ai-agent-rules.md
│  ├─ frontend-rules.md
│  ├─ backend-rules.md
│  └─ git-rules.md
└─ tasks/
   └─ task-template.md
```

---

## File Roles

### `AGENTS.md`

The main instruction file for AI coding agents.

AI tools should read this file first before editing a project.

It defines:

- Required reading order
- Core AI behavior
- Editing rules
- Forbidden actions
- Final response format

---

### `prompts/base-prompt.md`

The base prompt for starting an AI coding session.

Use this when opening a project in Codex, Claude Code, Cursor, or another AI coding tool.

---

### `prompts/apply-to-project.md`

A prompt for applying the `harnessE` structure to an existing project.

Use this when you want to add:

- `AGENTS.md`
- `docs/`
- `rules/`
- `tasks/`

to another project.

---

### `prompts/feature-prompt.md`

A reusable prompt for asking an AI agent to add a new feature.

---

### `prompts/refactor-prompt.md`

A reusable prompt for asking an AI agent to refactor existing code safely.

---

### `prompts/review-prompt.md`

A reusable prompt for asking an AI agent to review code without modifying it.

---

### `docs/project-context.md`

Describes the project purpose, target users, core features, tech stack, and current development status.

AI agents should read this before making project-specific changes.

---

### `docs/architecture.md`

Defines the recommended project architecture.

It explains how to organize:

- Pages
- Components
- Features
- Hooks
- Services
- Utilities
- Assets
- Styles
- Backend routes, controllers, services, and models

---

### `docs/coding-convention.md`

Defines coding conventions for consistent development.

It explains naming, component structure, API rules, CSS rules, comments, and error handling.

---

### `docs/workflow.md`

Defines the standard workflow AI agents must follow:

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

### `docs/checklist.md`

A checklist for reviewing AI-generated changes before completion.

It includes:

- Code safety
- Architecture
- Frontend checks
- Backend checks
- Git checks
- Final response checks

---

### `rules/ai-agent-rules.md`

Defines general rules for AI agents.

This file explains what AI agents must do and what they must avoid.

---

### `rules/frontend-rules.md`

Defines frontend-specific rules for React, JavaScript, Vite, CSS, components, state, API calls, and accessibility.

---

### `rules/backend-rules.md`

Defines backend-specific rules for routes, controllers, services, models, middlewares, validation, errors, and security.

---

### `rules/git-rules.md`

Defines Git branch, commit, and pull request rules.

---

### `tasks/task-template.md`

A reusable task template for giving clear instructions to an AI coding agent.

---

## How to Use harnessE in Another Project

### 1. Open your target project in VSCode

Example:

```bash
cd your-project
code .
```

### 2. Ask your AI coding tool to apply harnessE

Use this prompt:

```txt
Apply the harnessE standard to this project.

Read AGENTS.md and prompts/base-prompt.md from the harnessE repository first.

Create or update:
- AGENTS.md
- docs/project-context.md
- docs/architecture.md
- docs/coding-convention.md
- docs/workflow.md
- docs/checklist.md
- rules/ai-agent-rules.md
- rules/frontend-rules.md
- rules/backend-rules.md
- rules/git-rules.md
- tasks/task-template.md

Analyze the current project structure and write project-specific documentation.

Do not modify existing feature code.
Do not delete existing files.
Do not install new packages.

After finishing, summarize created files, modified files, and how to use the harness in future AI sessions.
```

---

## Base Prompt for AI Coding Tools

When starting a new AI coding session, use:

```txt
Read AGENTS.md first.
Then read prompts/base-prompt.md.
Follow the harnessE standard before editing this project.

Before changing code:
1. Inspect the project structure.
2. Find related files.
3. Explain the intended change briefly.
4. Modify only necessary files.
5. Summarize changed files and test steps.
```

---

## Recommended Frontend Structure

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

## Recommended Backend Structure

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

## Core Rules

AI agents using `harnessE` must:

- Read project instructions before editing.
- Inspect related files before changing code.
- Modify only task-related files.
- Preserve existing behavior unless changes are requested.
- Keep changes small and reviewable.
- Follow the existing project style.
- Separate UI, logic, API calls, and utilities.
- Avoid unnecessary dependencies.
- Avoid hard-coded URLs.
- Never expose secrets or API keys.
- Provide a final summary and test steps.

---

## Forbidden AI Behavior

AI agents must not:

- Rewrite the whole project without permission.
- Modify unrelated files.
- Delete existing files without permission.
- Rename major folders without permission.
- Add unnecessary packages.
- Commit `.env` files.
- Expose secrets or API keys.
- Skip file inspection.
- Skip the final summary.

---

## Final Response Standard

After completing any task, AI agents should respond with:

```txt
Summary:
- What was done

Changed files:
- file 1: what changed
- file 2: what changed

Important details:
- Key implementation choices

How to test:
- Test step 1
- Test step 2

Risks or follow-up:
- Anything that should be checked later
```

---

## Recommended Commit Message Format

```txt
type: short description
```

Examples:

```txt
docs: update harness engineering guide
feat: add memory upload form
fix: resolve login redirect issue
refactor: separate API services from components
```

---

## Why harnessE Exists

AI tools are useful, but without clear rules they may:

- Modify unrelated files
- Rewrite too much code
- Ignore existing architecture
- Mix API logic into UI components
- Skip error handling
- Produce changes that are hard to review

`harnessE` prevents this by giving every AI agent the same working standard.

---

## Main Principle

```txt
safe change > fast change
small edit > large rewrite
existing pattern > new pattern
clear code > clever code
human reviewability > automatic completion
```

---

## License

This repository is intended to be reused as a personal or team AI development standard.

## Slash Command Templates

harnessE provides reusable slash-command-style prompt templates.

Common commands:

```txt
/apply-harness
/feature
/refactor
/review
/fix
/gpush

## Codex Slash-Style Commands

harnessE is designed for Codex usage.

The `commands/` folder contains slash-style command templates.

Available commands:

```txt
/apply-harness
/feature
/refactor
/review
/fix
/gpush


---

## 11. Git 업로드

```bash
git add AGENTS.md README.md commands
git commit -m "docs: add codex command templates"
git push origin main