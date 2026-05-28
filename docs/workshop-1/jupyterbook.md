# JupyterBook & MyST

!!! note "This page is a stub"
    Content will be added after the workshop. For now, see the links below.

[JupyterBook](https://jupyterbook.org) is a tool for building publication-quality books and documents from Jupyter Notebooks and Markdown. It uses [MyST Markdown](https://mystmd.org/) — a flavour of Markdown designed for scientific and technical writing.

## When to use it

JupyterBook is a good fit when your content is:

- Jupyter Notebooks with outputs you want to display
- Linear, book-like structure (chapters, sections)
- Heavy on cross-references, citations, or equations
- Aimed at teaching or tutorials

## Examples in the wild

- [OGGM tutorials](https://tutorials.oggm.org)
- [Quantifying Climate Risks (Fabien Maussion)](https://fabienmaussion.info/climate_risks)
- [OGGM educational platform](https://edu.oggm.org)
- [The official JupyterBook gallery](https://executablebooks.org/en/latest/gallery/)

## Key links

- :material-book-open: [JupyterBook documentation](https://jupyterbook.org)
- :material-book-open: [MyST Markdown documentation](https://mystmd.org)
- :fontawesome-brands-github: [JupyterBook on GitHub](https://github.com/executablebooks/jupyter-book)

## Quick start

```bash
pip install jupyter-book
jupyter-book create mybook/
jupyter-book build mybook/
```

See the [official quickstart guide](https://jupyterbook.org/en/stable/start/your-first-book.html) for a full walkthrough.
