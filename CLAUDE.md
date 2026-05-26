# Project: j-yfan.github.io

Personal website for Jing-Yuan Fan, deployed via GitHub Pages from this repo's `main` branch. Single-file site (`index.html`) with two switchable visual styles (Claude Code / Apple) and inline CSS + JS.

## Git workflow (durable, user-authorized 2026-05-25)

**Auto-commit + push at the end of every turn that edits files.** No confirmation needed.

- Stage only the files actually changed (avoid `git add -A` / `git add .`).
- Use a clean, descriptive commit message — one-line summary in imperative mood (e.g. `Add scroll-spy side nav`), optional body for multi-file changes.
- Include the standard `Co-Authored-By: Claude ...` trailer.
- Push to `origin/main` immediately after the commit.

Skip the commit only if: the turn changed no files, or the change is in-progress / broken — in which case mention it in your reply so the user can decide.

## Project conventions

- **No build step.** Editing `index.html` and pushing to `main` deploys directly via GitHub Pages — no CI, no bundler, no lockfile, no `package.json`.
- **Verify manually:** `open index.html` in a browser. No test suite, no linter.
- **Pre-paint theme script must stay inline in `<head>`.** The synchronous `localStorage.getItem("site-theme")` read inside the inline `<script>` in `<head>` prevents a flash of the wrong theme on reload. Don't move it to `<body>`, don't add `defer`/`async`, don't externalize it.
- **Theme variables come in pairs.** Every CSS custom property must be defined in both `:root` (Claude Code, default) and `html[data-theme="apple"]` (Apple). The toggle assumes every variable has a value in both blocks.
- **Scroll-spy section IDs are load-bearing.** The four `<section>`s in `<main>` use IDs `home`, `work`, `cad`, `contact`. These are hardcoded in the JS `sectionEls` array and the side-nav `data-target` attributes. To add or rename a section, update the HTML, the side-nav `<ul>`, and the JS array together.
- **`<!-- TODO: replace ... -->` comments mark content slots** for project cards, publications, and CAD media that the user will fill later. Preserve them when restructuring nearby markup.
