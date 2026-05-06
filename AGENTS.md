# AGENTS.md

## Purpose

This repository is a reusable harness engineering template for AI-assisted software development.

Any AI coding agent should use this repository as the standard guide before modifying a project.

## Core Rule

Before changing any code, the AI agent must understand the project structure, coding rules, and task goal.

## Required Reading Order

When applying this harness to another project, read these files in order:

1. `README.md`
2. `docs/project-context.md`
3. `docs/architecture.md`
4. `docs/coding-convention.md`
5. `docs/workflow.md`
6. `docs/checklist.md`
7. Related files in `rules/`

## AI Agent Rules

1. Do not modify unrelated files.
2. Do not rewrite the whole project unless explicitly requested.
3. Keep changes small and testable.
4. Explain which files will be changed before editing.
5. Follow the existing project architecture.
6. Separate UI, business logic, API calls, and utility functions.
7. Use environment variables instead of hard-coded URLs.
8. After editing, provide a summary, changed files, and test steps.

## Required Final Response Format

After completing work, respond with:

- Summary
- Changed files
- Important details
- How to test
- Possible risks or follow-up improvements