# Project: j-yfan.github.io

Personal website for Jing-Yuan Fan, deployed via GitHub Pages from this repo's `main` branch. Single-file site (`index.html`) with two switchable visual styles (Claude Code / Apple) and inline CSS + JS.

## Git workflow (durable, user-authorized 2026-05-25)

**Auto-commit + push at the end of every turn that edits files.** No confirmation needed.

- Stage only the files actually changed (avoid `git add -A` / `git add .`).
- Use a clean, descriptive commit message — one-line summary in imperative mood (e.g. `Add scroll-spy side nav`), optional body for multi-file changes.
- Include the standard `Co-Authored-By: Claude ...` trailer.
- Push to `origin/main` immediately after the commit.

Skip the commit only if: the turn changed no files, or the change is in-progress / broken — in which case mention it in your reply so the user can decide.
