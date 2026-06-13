# 3.1 MkDocs & Material

[MkDocs](https://www.mkdocs.org/) is a fast, simple static site generator built around Markdown. Paired with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme — which is what almost everyone uses — it produces clean, professional-looking websites with a rich feature set out of the box: responsive design, built-in search, dark mode, syntax highlighting, and more.

**This very site is built with MkDocs Material.** If you like what you see here, you can have the same thing running in under an hour.

!!! note "MkDocs vs Material"

    MkDocs is the build engine; Material is the theme. In practice, nearly everyone installs them together and treats them as a single tool. Installing Material also installs MkDocs, so `mamba/conda/pip install mkdocs-material` is all you need.

## What is it good for?

MkDocs works best for **documentation and project websites** — situations where content is organised into pages, navigation matters, and you want something that looks polished with minimal effort. See the [tool comparison table](intro-static-sites.md#the-tools-we-cover-today) for a fuller picture of when to use MkDocs versus JupyterBook or Jekyll.

It is less suited to: long-form books with heavy cross-referencing (use JupyterBook/MyST), or highly customised personal websites with unique layouts (use Jekyll).

## Getting started

The [official documentation](https://squidfunk.github.io/mkdocs-material/getting-started/) covers everything, but the core workflow is:

### 1. Install

~~~bash
pip install mkdocs-material
~~~

### 2. Create a new project

~~~bash
mkdocs new my-project
cd my-project
~~~

This creates a minimal project with a `mkdocs.yml` configuration file and a `docs/` folder containing a single `index.md`.

### 3. Enable the Material theme

Edit `mkdocs.yml`:

~~~yaml
site_name: My Project
theme:
  name: material
~~~

### 4. Preview locally

~~~bash
mkdocs serve
~~~

Open `http://127.0.0.1:8000` in your browser. The site rebuilds automatically as you edit files.

### 5. Deploy

~~~bash
mkdocs gh-deploy
~~~

This builds the site and pushes it to the `gh-pages` branch of your GitHub repository. Enable Pages in the repository settings and your site is live. Alternatively, use a [GitHub Actions workflow](https://squidfunk.github.io/mkdocs-material/publishing-your-site/) for automatic deployment on every push.

## The plugin ecosystem

One of MkDocs Material's strengths is its plugin ecosystem. A few plugins we find particularly useful:

| Plugin | What it does |
| --- | --- |
| [`mkdocs-jupyter`](https://github.com/danielfrg/mkdocs-jupyter) | Render Jupyter Notebooks as pages (no need to export first) |
| [`mkdocstrings`](https://mkdocstrings.github.io/) | Auto-generate API reference pages from Python docstrings |
| [`mkdocs-bibtex`](https://github.com/shyamd/mkdocs-bibtex) | BibTeX citation support |
| [`mkdocs-git-revision-date-localized`](https://github.com/timvink/mkdocs-git-revision-date-localized) | Show "last updated" dates on pages from git history |
| [Blog plugin](https://squidfunk.github.io/mkdocs-material/plugins/blog/) | Full blog support with tags and pagination — built into Material (no extra install) |

Plugins are declared in `mkdocs.yml` under the `plugins:` key and installed via `pip`.

## The `mkdocs.yml` file

All configuration lives in a single `mkdocs.yml` file at the root of the project. Beyond the basics (site name, theme, navigation), it controls extensions, plugins, and appearance. The [Material setup documentation](https://squidfunk.github.io/mkdocs-material/setup/) is the best reference for what is available — and there is a lot.
