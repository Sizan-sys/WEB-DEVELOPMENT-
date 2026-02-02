# Copilot instructions for Day_1 (static web sample)

This repo is a minimal static website. The guidance below is focused and actionable for an AI coding agent working in this codebase.

## Big picture
- **Type:** Single-page static site (no build system). Source files live in the `Day_1` folder.
- **Key files:** [Day_1/index.html](Day_1/index.html#L1-L14), [Day_1/script.js](Day_1/script.js), [Day_1/style.css](Day_1/style.css)
- **Runtime:** Served as static files in a browser. There is no server-side code or package manifest.

## What to know about the current code
- `index.html` is the entry point and currently contains duplicate `<body>` tags and no content. See [Day_1/index.html](Day_1/index.html#L1-L14).
- `script.js` and `style.css` exist but are empty; JS behaviors should be added to `script.js` and styles to `style.css`.

## Project-specific conventions & patterns
- Keep structure flat: add new pages and assets under `Day_1/` unless a new feature warrants a new folder.
- Keep JavaScript unobtrusive: attach listeners in `script.js` to elements rendered in `index.html` (no inline JS in HTML unless explicitly needed).
- Keep CSS in `style.css`; prefer class-based styling over inline styles.

## How to run & test locally
No build required. Serve the `Day_1` folder over HTTP for correct asset loading and CORS behavior.

Examples (run from the workspace root):
```powershell
# Serve on port 8000 with Python (works on Windows with Python installed)
python -m http.server 8000 --directory Day_1

# Open the default browser to the root (PowerShell)
Start-Process "http://localhost:8000"
```

Alternative (Node.js):
```bash
# if user prefers, install `serve` globally and run from the workspace root
npm install -g serve
serve Day_1 -p 8000
```

## Code-editing guidance for AI agents
- When modifying `index.html`, remove duplicate tags and produce valid HTML5 structure.
- Place DOM-ready initialization in `script.js`; e.g., wrap setup in `document.addEventListener('DOMContentLoaded', ...)`.
- If adding behavior that requires state, keep that state inside `script.js` and avoid polluting the global scope.
- Keep changes minimal and focused: this repo aims to be an educational/simple demo, not a production app.

## Examples from this repo
- Fix duplicate body tags in [Day_1/index.html](Day_1/index.html#L1-L14). Replace with a single `<body>` element and a placeholder container like `<main id="app"></main>`.
- Add basic DOM init in `script.js`:
```js
document.addEventListener('DOMContentLoaded', () => {
  const app = document.getElementById('app');
  if (app) app.textContent = 'Hello — page loaded.';
});
```

## Integration points & external dependencies
- There are no external integrations configured. If you introduce third-party libs, document them in a new `README.md` and add an install/run note.

## When to ask the user
- If a proposed change adds a build step, new dependencies, or a new folder layout, confirm before proceeding.
- Ask for design or UX intent before adding non-trivial UI or behavior (this repo is likely a learning sample).

---
If anything here is unclear or you want the instructions expanded with more examples or a different tone, tell me what to add or change.
