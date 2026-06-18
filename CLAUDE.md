# CLAUDE.md — Geog Digital Tools Workshop Site

## Project overview

MkDocs Material site for a workshop series on open-source tools for geographic researchers.
Hosted at [bristol-glaciology.github.io/geog-digital-tools](https://bristol-glaciology.github.io/geog-digital-tools/) via GitHub Pages.
Organised by Fabien Maussion and Tom Chudley (Bristol Glaciology Centre).

## Workshop 1 — Status (as of 2026-06-14) — reference pages done, hands-on pending

Workshop date: **19 June 2026**. About 30 participants, mix of technical backgrounds (some human geographers with limited tech skills).

### Philosophy

- Opinionated intro: tell people what we use and why, not an exhaustive survey
- Get people to official docs ASAP rather than duplicating them
- Low-tech-skill audience: avoid jargon, assume no git/command-line knowledge for the main path
- DEI: use active voice, simpler sentences, and well-ordered clauses

### File structure (all under `docs/workshop-1/`)

| File | Author | Status |
| --- | --- | --- |
| `index.md` | — | Done — announcement page, programme (Parts 1–3), lightning talk list, "How to prepare" |
| `intro-static-sites.md` | Fabien | **Done** — static vs dynamic, alternatives (WordPress etc.), tool comparison table with examples, "which one?" tip box |
| `markdown-and-notebooks.md` | Tom | **Done** — ported from prep_hackmd, cleaned up, simplified notebooks section |
| `installation.md` | Fabien | **Done** — micromamba (recommended) + Anaconda, platform tabs, MkDocs & JupyterBook install steps; **not in nav** (linked only from "How to prepare") |
| `mkdocs.md` | Fabien | **Done** — intro, getting started steps, plugin table, mkdocs.yml overview |
| `jupyterbook.md` | Tom | **Done** — ported from `prep_hackmd/3.3 JupyterBook & MyST.md`, fixed admonition and analogy |
| `jekyll.md` | Tom | **Done** — ported from `prep_hackmd/3.4 Jekyll.md`, fixed malformed admonition (body was in fenced block) |
| `sphinx.md` | Fabien | **Done** — what it is, RST, how it differs from MkDocs, when to use it |
| `hosting.md` | Fabien | **Done** — server explainer, hosting options, GitHub Pages recommendation, ReadTheDocs, custom domains (analytics moved to `legal.md`) |
| `legal.md` | Fabien | **Done** — "I'm not a lawyer" intro; privacy policy & who's in charge, data minimisation, cookies/web analytics (moved from hosting), image copyright |
| `git-intro.md` | Fabien | **Done** — conceptual page: what is git/GitHub, why it's needed for hosting, encouragement + resources |
| `hands-on.md` | — | **Done** — router page; grid cards + shared three-stage framing (get template → preview locally → publish optionally; only publishing needs a GitHub account) |
| `hands-on-jekyll.md` | Tom | **Done** — web-GUI tutorial (headline, no install, needs account) + local route as no-account alternative. Local Ruby install instructions are a TODO (see below) |
| `hands-on-mkdocs.md` | Tom | **Done** — local-first; added ZIP-download (no-account) option, publishing marked optional |
| `hands-on-jupyterbook.md` | Tom | **Done** — local-first; added ZIP-download (no-account) option, publishing marked optional |

`prep_hackmd/git-hands-on.md` — Tom's original Jekyll hands-on tutorial (superseded by `hands-on-jekyll.md`; kept for reference).

### Hands-on design principle (agreed 2026-06-15)

Every path follows the same three stages so nobody is blocked at the door:
1. **Get the template** — download ZIP (no account) or fork (account).
2. **Edit & preview locally** — install tool, build on own machine. No account.
3. **Publish (optional)** — GitHub Pages; the *only* stage needing an account.

Jekyll additionally keeps its zero-install web-GUI route (needs a free account) as the recommended easy path for non-CLI users.

### mkdocs.yml nav (current)

```yaml
nav:
  - Home: index.md
  - Workshop 1:
    - Overview: workshop-1/index.md
    - 1. Static site generators: workshop-1/intro-static-sites.md
    - 2. Markdown & Notebooks: workshop-1/markdown-and-notebooks.md
    - 3. The tools:
      - 3.1 MkDocs & Material: workshop-1/mkdocs.md
      - 3.2 JupyterBook: workshop-1/jupyterbook.md
      - 3.3 Jekyll: workshop-1/jekyll.md
      - 3.4 Sphinx: workshop-1/sphinx.md
    - 4. Hosting: workshop-1/hosting.md
    - 5. Legal aspects: workshop-1/legal.md
    - 6. Git basics: workshop-1/git-intro.md
    - 7. Hands-on tutorial:
      - 7.1 Introduction: workshop-1/hands-on.md
      - 7.2 Jekyll: workshop-1/hands-on-jekyll.md
      - 7.3 MkDocs & Material: workshop-1/hands-on-mkdocs.md
      - 7.4 JupyterBook: workshop-1/hands-on-jupyterbook.md
```

`installation.md` is intentionally excluded from the nav — it is a prerequisite page, not a programme section.

### Remaining TODO

- **Jekyll local install** (`hands-on-jekyll.md`): **finalised** — two routes documented as tabs:
  - **micromamba/conda:** `micromamba create -n jekyll -c conda-forge ruby cxx-compiler make`, activate, `gem install bundler jekyll`. Note: needs `cxx-compiler` (C++) — `c-compiler` alone fails on native gems (eventmachine, sass-embedded) — and the env must be activated when running `gem`/`bundle`. **Verified end-to-end on macOS** (2026-06-17, full build of `example-jekyll-website` template succeeds). **Untested on Windows/Linux** — flagged in-page with a low-key note; Fabien to ask an RSE to test.
  - **native Ruby:** Homebrew (macOS), RubyInstaller + DevKit (Windows), `apt install ruby-full build-essential` (Linux).
  - Open decision (with Tom): whether to fold the conda route into `installation.md` for one unified install page, once Windows/Linux are confirmed.
- Review and iteration with Tom before the workshop (19 June 2026)

## Build and deploy

```bash
pip install -r requirements.txt
mkdocs serve          # local preview at http://127.0.0.1:8000
mkdocs gh-deploy      # deploy to GitHub Pages
```

The site auto-deploys via GitHub Actions on push to main (check `.github/workflows/`).
