# MkDocs & Material

!!! note "This page is a stub"
    Content will be added after the workshop. For now, see the links below.

[MkDocs](https://www.mkdocs.org/) is a fast, simple static site generator designed for project documentation. The [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme turns it into something genuinely beautiful and feature-rich.

!!! tip "Meta"
    This site is built with MkDocs + Material. You're looking at the output right now.

## When to use it

MkDocs + Material is a good fit when you need:

- Clean, navigable documentation for a tool, model, or project
- A simple config file (`mkdocs.yml`) and a folder of Markdown files
- Built-in search, versioning, and a responsive design
- Something that looks professional with minimal effort

## Examples in the wild

- [pDEMtools documentation](https://pdemtools.readthedocs.io)
- [Material for MkDocs itself](https://squidfunk.github.io/mkdocs-material/)
- [FastAPI documentation](https://fastapi.tiangolo.com) (MkDocs + Material)

## Key links

- :material-book-open: [MkDocs documentation](https://www.mkdocs.org/)
- :material-book-open: [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/)
- :material-creation: [Material setup guide](https://squidfunk.github.io/mkdocs-material/getting-started/)

## Quick start

```bash
pip install mkdocs-material
mkdocs new mysite/
cd mysite
# edit mkdocs.yml to add: theme: {name: material}
mkdocs serve  # live preview
mkdocs build  # build the site
```

See the [official getting started guide](https://squidfunk.github.io/mkdocs-material/getting-started/) for full details.
