# MkDocs Material Example Website

This is an example website using [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

## Prerequisites

- Python 3.7 or higher
- pip

## Installation

1. Install MkDocs and dependencies:
```bash
pip install -r requirements.txt
```

## Running Locally

To build and serve the site locally:

```bash
mkdocs serve
```

The site will be available at `http://localhost:8000`

## Building for Production

To build the site for production:

```bash
mkdocs build
```

The output will be in the `site/` directory.

## Structure

- `mkdocs.yml` - Site configuration
- `docs/` - Documentation pages
  - `index.md` - Home page
  - `research/` - Research and markdown examples
  - `coding/` - Coding examples
- `docs/assets/` - Images and other assets

## Publishing

To deploy to GitHub Pages:

```bash
mkdocs gh-deploy
```

(You'll need to have the repository configured properly for this to work.)
