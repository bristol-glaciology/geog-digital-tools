# 3.4 Sphinx (honourable mention)

[Sphinx](https://www.sphinx-doc.org/), created in 2008, set the standard for Python package documentation and remains so today. NumPy, SciPy, Django, and most major scientific libraries use Sphinx. We still use it, mostly because older projects run on it and work well enough that migrating offers no benefit.

!!! note "Jupyter Book v1 and Sphinx"

    Until the release of [Jupyter Book v2](https://jupyterbook.org/) in November 2025, which fully aligned Jupyter Book and MyST, [Jupyter Book v1](https://jupyterbook.org/v1/intro.html) was built using Sphinx. As a result, many Jupyter Book tutorials (and LLM output!) which have not updated to v1 will default to the Sphinx-style setup and language.

## How it differs from MkDocs

Sphinx uses [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) (RST), a richer but more verbose format than Markdown. RST has native support for cross-references, footnotes, directives, and complex tables. Markdown has been added via [MyST parser](https://myst-parser.readthedocs.io/), which works well, but most existing Sphinx projects use RST, so you'll encounter it often.

Sphinx scales well for large, deeply cross-referenced documentation (API generation, glossaries, inter-project linking). But it's also more complex to configure. MkDocs gets you to polished results faster; Sphinx pays off at scale.

## Should you start a new project with it?

Probably not, unless you're publishing a Python package and want to follow ecosystem conventions. For new projects, [MkDocs](mkdocs.md) or [JupyterBook](jupyterbook.md) get you to great results faster. But knowing Sphinx exists, and being able to read and edit an RST file is useful, given how much scientific Python documentation runs on it.
