# Geog Digital Tools & Infrastructure Series

Source repository for the workshop series website, hosted at https://bristol-glaciology.github.io/geog-digital-tools/

Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).

## Repository structure

```text
docs/          # Page content (Markdown)
mkdocs.yml     # Site configuration
requirements.txt
```

## Local development

Create and activate a conda environment:

```bash
conda create -n mkdocs python=3.11
conda activate mkdocs
pip install -r requirements.txt
```

Then serve the site locally:

```bash
mkdocs serve
```

Open <http://127.0.0.1:8000> in your browser. The site reloads automatically on file changes.

## Deployment

Pushes to `main` automatically trigger a GitHub Actions build and deploy to GitHub Pages.
You can also deploy manually:

```bash
mkdocs gh-deploy
```

## License

Content is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — Bristol Glaciology Centre, University of Bristol.
