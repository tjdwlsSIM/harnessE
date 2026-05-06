
---

# 7. `rules/frontend-rules.md`

```md
# Frontend Rules

These rules apply to frontend projects using harnessE.

## Recommended Stack

- React
- JavaScript
- Vite
- CSS or CSS Modules
- React Router when routing is needed

## Component Rules

- Use functional components.
- Keep components focused.
- Use props for data input.
- Avoid deeply nested component logic.
- Extract repeated UI into reusable components.

## Page Rules

Pages should:

- Compose components
- Handle route-level layout
- Connect feature sections

Pages should not:

- Contain too much API logic
- Contain large utility functions
- Contain repeated UI blocks

## API Communication

API communication should live in `services/`.

Recommended:

```txt
src/services/authService.js
src/services/memoryService.js
src/services/uploadService.js