# /gpush

Use this command when the user wants to add, commit, and push Git changes in one flow.

## User Request

The text after `/gpush` is the commit message.

Example:

```txt
/gpush docs: update harnessE guide
```

Commit message:

```txt
docs: update harnessE guide
```

---

## Purpose

This command runs the standard Git upload flow:

```bash
git add .
git commit -m "[commit message]"
git push
```

---

## Required Steps

When the user runs `/gpush [commit message]`, Codex must:

1. Check the current Git status.
2. Stage all changes using `git add .`.
3. Commit using the message provided after `/gpush`.
4. Push to the current branch.

---

## Commands to Run

```bash
git status --short
git add .
git status --short
git commit -m "$ARGUMENTS"
git push
```

---

## Safety Rules

Before committing, Codex should check whether sensitive or unnecessary files are being staged.

Be careful with:

```txt
.env
.env.local
.env.production
node_modules/
dist/
build/
.DS_Store
```

If these files appear in `git status --short`, Codex should stop and warn the user before committing.

---

## Commit Message Rule

The commit message must come from the text after `/gpush`.

Recommended format:

```txt
type: short description
```

Examples:

```txt
docs: update harnessE guide
feat: add upload preview
fix: resolve login redirect issue
refactor: separate API services
chore: update project config
```

---

## If No Commit Message Is Provided

If the user runs only:

```txt
/gpush
```

Codex should not commit immediately.

Instead, Codex should inspect the changed files and suggest a commit message.

Example response:

```txt
Commit message is missing.

Suggested commit message:
docs: update harnessE command templates

Run:
/gpush docs: update harnessE command templates
```

---

## Final Response Format

After completing the Git upload, respond with:

```txt
Summary:
- Staged all changes with git add .
- Created commit with message: [commit message]
- Pushed to the current branch

Git result:
- Branch:
- Commit message:
- Push status:
```