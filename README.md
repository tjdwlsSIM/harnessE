# harnessE

`harnessE` is a reusable harness engineering repository for AI-assisted development.

It provides common rules, prompts, and workflows so that different AI coding tools can work consistently across projects.

## Main Use Case

Use this repository when you want an AI coding agent to:

- Understand project context first
- Follow a consistent architecture
- Avoid modifying unrelated code
- Apply frontend/backend coding rules
- Generate predictable implementation summaries
- Work safely across different projects

## Recommended Usage

In another project, give the AI this instruction:

```txt
Use the harnessE repository as the harness engineering standard.
Read AGENTS.md first.
Then apply the docs, rules, and prompts structure to this project.
Do not modify unrelated source code.