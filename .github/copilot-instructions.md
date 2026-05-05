## Purpose

This repository is a Jekyll-based personal website (Academic Pages theme). These instructions give an AI coding agent immediate, actionable context: the architecture, developer workflows, file patterns, and integration points so the agent can make safe, project-aligned edits.

## Quick contract (2–3 bullets)
- Input: edits to content, templates, assets, or small scripts in this repo. Output: updated markdown, Liquid templates, SCSS, JS, or small Python helpers that follow existing conventions.
- Keep changes minimal and reversible: prefer editing `_includes/` or `_layouts/` and add tests or a short preview step (see "How to preview locally").

## Big picture (what this repo is)
- Static site powered by Jekyll using the Academic Pages / Minimal Mistakes variant.
- Key directories:
  - `_layouts/` and `_includes/` — site templates and partials (visual and structural changes go here).
  - `_posts/`, `_publications/`, `_talks/`, `_portfolio/` — content collections. Files here are markdown with YAML front matter.
  - `_sass/` — SCSS partials.
  - `assets/js/` — JS source; `assets/js/main.min.js` is the built/minified JS produced by npm scripts.
  - `markdown_generator/` — python/jupyter helpers that generate markdown (publications/talks) from TSV/CSV.
  - `files/` — static downloadable files served at `/files/...`.

## Project-specific conventions (concrete examples)
- Front-matter & filenames: content under `_publications` and `_posts` uses date-prefixed filenames like `YYYY-MM-DD-slug.md` (see `_publications/2015-10-01-paper-title-number-3.md`).
- Defaults are centralized in `_config.yml` (see `defaults:` block) — many collection-level defaults (layout, author_profile, read_time) are applied automatically.
- Collections are declared in `_config.yml` (e.g. `publications`, `talks`, `teaching`) and use `output: true` and `permalink: /:collection/:path/`.
- JS build: `package.json` provides `npm run build:js` (uglify) and `npm run watch:js`. Use these to regenerate `assets/js/main.min.js` after editing JS plugins or `_main.js`.

## Build / preview / common commands (PowerShell examples)
Install and prepare:
```powershell
# Ruby + gems
bundle install

# Node deps for asset tooling
npm install
```
Preview locally (use `bundle exec` to match GitHub Pages environment):
```powershell
bundle exec jekyll serve -l -H localhost
```
Build or regenerate JS only:
```powershell
npm run build:js
npm run watch:js   # rebuilds on JS changes
```
Notes: Gemfile uses the `github-pages` gem and includes `wdm` for Windows. Always run Jekyll via `bundle exec` to ensure gem versions match CI/GitHub Pages.

## Cross-component flows & integration points
- GitHub Pages: repo uses `github-pages` gem (see `Gemfile`) so local runs should behave like Pages. CI badge in `README.md` shows Pages workflow usage.
- JS pipeline: `package.json` uglifies jQuery + plugin files into `assets/js/main.min.js`. When changing JS, run `npm run build:js`.
- Content generation: `markdown_generator/` and `talkmap.py` produce markdown files for `/_publications` and `/_talks`. If you change the format of generated markdown, update consumers (layouts/includes) accordingly.

## Safe edit rules for an AI agent (do these always)
- Prefer small, focused patches. For UI/template changes: edit one file under `_includes/` or `_layouts/` and preview locally.
- When changing dependencies (Gemfile/package.json), add a short note in the PR describing why and the verification steps. Don't upgrade major versions without human review.
- When modifying content (e.g. adding a publication), follow existing front-matter keys and filename patterns. Example front matter for a publication file in `_publications/`:
  ```yaml
  ---
  title: "Paper Title"
  date: 2015-10-01
  categories: [conferences]
  layout: single
  ---
  ```

## Files to consult when making changes
- `_config.yml` — global defaults, collections, plugin whitelist, excluded files.
- `Gemfile` — Ruby/Jekyll dependencies (uses `github-pages`); Windows-friendly gem `wdm` included.
- `package.json` — JS build scripts (`uglify`, `build:js`, `watch:js`).
- `_layouts/` and `_includes/` — where to change markup and structure.
- `markdown_generator/` and `talkmap.py`/`talkmap.ipynb` — data-to-markdown generators.

## What not to change without human sign-off
- Major theme upgrades, gem or npm major-version bumps, and global permalink/permalink-style changes.
- Changing collection names or the `defaults:` block in `_config.yml` (these affect many pages).

If anything here is unclear or you want more details (for example: typical front-matter fields for publications, or how the `talkmap` generator is used), tell me which section to expand and I will iterate.
