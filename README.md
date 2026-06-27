# site/ — GitHub Pages output

This folder is the GitHub Pages repo content. The recipe page renderer writes `index.html`
here and pushes via `git` after each phase.

## Setup

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
