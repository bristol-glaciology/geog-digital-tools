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
| `hosting.md` | Fabien | **Done** — server explainer, hosting options, GitHub Pages recommendation, ReadTheDocs, analytics (incl. Plausible/GDPR/ethics) |
| `git-intro.md` | Fabien | **Done** — conceptual page: what is git/GitHub, why it's needed for hosting, encouragement + resources |
| `hands-on.md` | — | **Placeholder** — three sections (Jekyll / MkDocs / JupyterBook paths), content pending Tom's input |

`prep_hackmd/git-hands-on.md` — Tom's original Jekyll hands-on tutorial (moved back from `docs/`; will be incorporated into `hands-on.md` once path structure is agreed).

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
    - 5. Git basics: workshop-1/git-intro.md
    - Hands-on tutorial: workshop-1/hands-on.md
```

`installation.md` is intentionally excluded from the nav — it is a prerequisite page, not a programme section.

### Remaining TODO

- **Hands-on tutorial** (`hands-on.md`): waiting on Tom to clarify:
  - Which forkable repos to use for each path (Jekyll: is `bristol-glaciology/example-personal-website` still canonical? MkDocs/JupyterBook: will the templates in `example_websites/` be published as separate repos?)
  - Whether the three paths need equal depth or just the Jekyll one is a full tutorial
- Review and iteration with Tom before the workshop (19 June 2026)

## Build and deploy

```bash
pip install -r requirements.txt
mkdocs serve          # local preview at http://127.0.0.1:8000
mkdocs gh-deploy      # deploy to GitHub Pages
```

The site auto-deploys via GitHub Actions on push to main (check `.github/workflows/`).
