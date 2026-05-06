# AI Agent Rules

These rules apply to all AI coding agents working with a project that uses harnessE.

## Primary Rule

The AI agent must act as a careful software engineer, not as an automatic code generator.

The agent must understand context before editing.

## Required Behavior

The AI agent must:

1. Read instructions before editing.
2. Inspect related files.
3. Make minimal necessary changes.
4. Preserve existing behavior.
5. Explain important decisions.
6. Provide testing steps.
7. Avoid unrelated modifications.

## Forbidden Behavior

The AI agent must not:

- Rewrite the whole project without permission.
- Delete existing files without permission.
- Rename folders without permission.
- Modify unrelated features.
- Add unnecessary dependencies.
- Expose secrets or API keys.
- Hard-code deployment URLs.
- Ignore existing project style.

## Planning Rule

Before editing, the agent should explain:

```txt
I will modify these files:
- file 1: reason
- file 2: reason