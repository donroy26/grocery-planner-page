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

## Access gate (casual, client-side)

The page has a password screen. **This is a casual hide, NOT real security** — it's a static
public page, so the content is technically present in the page source and the repo regardless of
the gate; the JS only decides whether to *display* it. It keeps a casual visitor out, nothing more.

- Password is checked by SHA-256 in the browser. Only the **hash** lives in the page/config
  (`data/config.json` → `page_password_sha256`), never the plaintext.
- Current password: **doneats**. Unlock persists per-device (localStorage key `wgp-unlocked`).
- To change it: `python -c "import hashlib;print(hashlib.sha256(b'NEWPW').hexdigest())"`, paste the
  hash into `page_password_sha256` in config, re-run Phase 1 (or re-render). Set it to `""` to
  remove the gate. For *real* privacy, move to a private repo + an auth-enforcing host
  (Netlify/Cloudflare) — out of scope here.

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
