# Workflow

This document defines the standard workflow that AI coding agents must follow when working on a project using harnessE.

## 1. Understand Before Editing

Before editing code, the AI agent must:

1. Read `AGENTS.md`
2. Read relevant files in `docs/`
3. Inspect the current project structure
4. Identify the files related to the task
5. Explain the intended change briefly

The agent should not edit files before understanding the task context.

## 2. Task Execution Flow

Every task should follow this order:

```txt
Request → Context Check → File Inspection → Plan → Implementation → Review → Summary