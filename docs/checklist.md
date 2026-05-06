
---

# 5. `docs/checklist.md`

```md
# Checklist

This checklist must be used before finishing any AI-assisted coding task.

## Before Editing

- [ ] Read `AGENTS.md`
- [ ] Read relevant documents in `docs/`
- [ ] Checked current folder structure
- [ ] Identified related files
- [ ] Understood the task goal

## During Editing

- [ ] Modified only related files
- [ ] Kept changes small and focused
- [ ] Preserved existing behavior
- [ ] Followed naming conventions
- [ ] Separated UI, logic, API, and utilities
- [ ] Did not expose secrets or tokens
- [ ] Did not hard-code environment-specific URLs

## Frontend Checklist

- [ ] Component names are clear
- [ ] Repeated UI is extracted
- [ ] API logic is not inside UI components
- [ ] Loading state is handled
- [ ] Error state is handled
- [ ] Empty state is handled if needed
- [ ] Responsive layout is considered

## Backend Checklist

- [ ] Route logic is clear
- [ ] Controller/service separation is considered
- [ ] Request validation is handled
- [ ] Error responses are consistent
- [ ] Sensitive values are stored in environment variables

## Git Checklist

- [ ] Commit message is clear
- [ ] Unrelated files are not included
- [ ] Generated files are not accidentally committed
- [ ] `.env` files are ignored

## Final Response Checklist

The AI agent's final response must include:

- [ ] Summary
- [ ] Changed files
- [ ] Important implementation details
- [ ] How to test
- [ ] Risks or follow-up suggestions