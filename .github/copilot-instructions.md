<!-- .github/copilot-instructions.md - guidance for AI coding agents -->
# Copilot / AI Contributor Instructions

Purpose: Help AI agents edit and extend this repository safely and effectively.

- **Big picture**: This repository is a minimal static website. The primary entry point is `index.html` at the repo root. There is no build system, server code, or package manifest. Changes should prefer small, incremental edits to `index.html` or adding simple asset files (images/CSS/JS) in a new `assets/` folder.

- **Primary files**:
  - `index.html`: single-page content, minimal head/meta tags. Edit here for layout/content changes.
  - `README.md`: short project description and any developer notes.

- **Architecture & why**:
  - Intentionally simple: no frameworks or tooling. The site is meant to be edited directly and previewed in a browser. Avoid introducing heavy tooling unless requested by a human maintainer.

- **Developer workflow (what humans do, and what the AI should assume)**:
  - Edit `index.html` and place static assets under `assets/` (create the folder if needed).
  - Preview locally by opening `index.html` in a browser (or using a Live Server extension). No `npm`/`pip`/build step is required.
  - Commit messages: use conventional short prefixes, e.g. `feat: add hero section`, `fix: correct meta tag`, `chore: add assets folder`.

- **Project-specific conventions / patterns**:
  - Keep markup semantic and minimal (use `<section id="...">`, `<header>`, `<main>`, `<footer>`).
  - Preserve `<!DOCTYPE html>` and basic `<meta charset>` / viewport tags when editing `index.html`.
  - Prefer adding new files under `assets/` rather than scattering files at repo root.

- **When proposing larger changes**:
  - If adding a build/tooling layer (e.g., `package.json`, bundler), include in the PR a short migration plan in `README.md` describing the new workflow and how to preview locally.
  - Avoid adding external dependencies without explicit human approval.

- **Examples (concrete edits the AI might make)**:
  - Update the page title: change the `<title>` text in `index.html`.
  - Add a hero section: insert `<section id="hero">` after the opening `<body>`.
  - Add an `assets/styles.css` file and a single `<link rel="stylesheet" href="assets/styles.css">` in the head.

- **What not to do**:
  - Do not scaffold a full JS framework (React/Vite/etc.) or modify remote CI settings without human review.
  - Do not assume tests/builds exist—there are none to run by default.

- **Merge / PR guidance**:
  - Keep PRs small and focused (single feature/fix). Include screenshots or a short note on how to preview changes.

If any part of the repo changes to include tooling, server code, or tests, ask the maintainer before making broad architectural changes. Request clarification if you need a build/test command or where to place new modules.

---
Please review this guidance and tell me any missing specifics or preferences to include.
