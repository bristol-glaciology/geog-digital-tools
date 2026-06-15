# 3.4 Sphinx (honourable mention)

[Sphinx](https://www.sphinx-doc.org/) is the documentation tool that predates everything else on this list. Created in 2008 to document Python itself, it became the standard for Python package documentation and remains so today. If you have ever browsed the docs for NumPy, SciPy, Django, or any major scientific Python library, you have used a Sphinx site. We still use it extensively ourselves — mostly because our older projects were built with it before the alternatives existed, and it works well enough that there is no compelling reason to migrate.

!!! note "Jupyter Book v1 and Sphinx"

    Until the release of [Jupyter Book v2](https://jupyterbook.org/) in November 2025, which fully aligned Jupyter Book and MyST, [Jupyter Book v1](https://jupyterbook.org/v1/intro.html) was built using Sphinx. As a result, many Jupyter Book tutorials (and LLM output!) which have not updated to v1 will default to the Sphinx-style setup and language.

## How it differs from MkDocs

The most visible difference is the markup language. Sphinx was built around [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) (RST), a richer but more verbose format than Markdown. RST has native support for things Markdown needs extensions for: cross-references, footnotes, directives, and complex tables. Markdown support has been bolted on via the [MyST parser](https://myst-parser.readthedocs.io/), which works well — but RST is still the language of most existing Sphinx projects, so you will encounter it.

Beyond markup, Sphinx is considerably more powerful for large, deeply cross-referenced documentation sets (full API reference generation, glossaries, inter-project linking), but also considerably more complex to configure. MkDocs is faster to set up and produces visually polished results with almost no effort; Sphinx rewards patience and pays off at scale.

## Should you start a new project with it?

Probably not, unless you are publishing a Python package and want to follow ecosystem conventions. For new projects, [MkDocs](mkdocs.md) or [JupyterBook](jupyterbook.md) will get you to a great result faster. But knowing Sphinx exists — and being able to read and lightly edit an RST file — is a useful skill given how much of the scientific Python documentation landscape runs on it.
