# Instructions for Claude Code

This repo is a **single static page** to publish on GitHub Pages. There is no build step.
Do not add a framework, bundler, `package.json`, or compile step — keep it dependency-free.

## Goal

Publish `index.html` at `https://<user>.github.io/s4-do-lattice/`.

## Tasks

1. **Set author name.** Replace `Bertram Ludäscher` in `LICENSE` if a different copyright
   holder is wanted. Otherwise leave as is.

2. **Create the repo and push.** Suggested name: `s4-do-lattice`. From this directory:
   ```
   git init
   git add .
   git commit -m "Initial commit: S4 / DO-semantics lattice explorer"
   gh repo create s4-do-lattice --public --source=. --remote=origin --push
   ```
   (If `gh` is not available, create the repo on github.com and `git remote add origin … && git push -u origin main`.)

3. **Enable GitHub Pages.** Either via CLI:
   ```
   gh api -X POST repos/{owner}/s4-do-lattice/pages -f "source[branch]=main" -f "source[path]=/" 2>/dev/null || true
   ```
   or tell the user to do it manually: **Settings → Pages → Source → Deploy from a branch →
   `main` / `/ (root)` → Save.**

4. **Verify.** After ~60s, confirm the page loads at
   `https://<user>.github.io/s4-do-lattice/` and report the URL.

5. **Update the README link.** If the final URL differs from
   `https://ludaesch.github.io/s4-do-lattice/`, fix the `Live:` line in `README.md`.

## Notes / constraints

- `index.html` is fully self-contained: inline CSS + vanilla JS, no local assets. The only
  external request is the Google Fonts `@import`; it degrades gracefully to serif/mono if
  blocked. Do **not** introduce a `base` path or rewrite asset URLs — there are none.
- If the user asks to remove the Google Fonts dependency (e.g. for privacy/offline), the
  fonts to replace are Fraunces (display), Newsreader (body), Spline Sans Mono (mono).
  Swap the `@import` line and the `font-family` declarations for a system-font stack, or
  self-host the woff2 files under a `fonts/` dir and reference them with relative paths.
- Keep everything in one file unless the user explicitly asks to split it.

## Optional follow-ups (only if asked)

- Add an Actions workflow (`.github/workflows/deploy.yml`) for push-to-deploy. Not needed
  for a single static file — "Deploy from a branch" already auto-deploys on push.
- Add a screenshot/OpenGraph image for nicer link previews.
