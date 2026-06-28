# site/ — GitHub Pages output

This folder is the GitHub Pages repo content. The recipe page renderer writes `index.html`
here and pushes via `git` after each phase.

## ✅ Configured (2026-06-27)

- **Repo:** https://github.com/donroy26/grocery-planner-page (this `site/` is a git repo, remote `origin`).
- **Live URL:** **https://donroy26.github.io/grocery-planner-page/**
- Pages deploys from `main` branch root. `git_push_site()` auto-commits + pushes after each phase,
  so the live page updates every weekly run with no manual step.
- Auth: GitHub CLI (`gh`) is installed user-scope and logged in as `donroy26`; git uses the
  credential stored by that login. If pushes start failing with auth errors, re-run `gh auth login`.

## Setup (reference — already done above)

1. Create a GitHub repo for your GitHub Pages site (e.g., `yourusername.github.io/meals`).
2. Clone it into this `site/` folder:
   ```
   cd System/
   rmdir /s /q site          (Windows, removes placeholder)
   git clone https://github.com/yourusername/meals-page.git site
   ```
3. Enable GitHub Pages on the repo (Settings → Pages → deploy from `main` branch root).

Until this is configured, the renderer writes HTML locally to `site/index.html` and skips the push.
The system works fully without this (grocery list + plan-review still produced).
