# 2. Writing content: Markdown and Notebooks

Static site generators convert two basic formats into web pages: [Markdown](https://www.markdownguide.org/) for text and [Jupyter Notebooks](https://jupyter.org/) for code.

We will break this down into two halves: writing pure text using Markdown, and managing code workflows with Jupyter Notebooks.

## 1: Writing with Markdown

If you have ever formatted a text file or written a `README` file on GitHub, you have likely already encountered Markdown.
Markdown is a lightweight markup language created in 2004. Unlike Word (`.docx`) which hides complex XML styling code under the hood, Markdown files are plain text (`.md`) with simple characters for formatting: `#` for headings, `**bold**` for bold, etc. Markdown files are just plain text identical to any `.txt` file, just with a different file extension (`.md`) to communicate that Markdown is being used.

It is human-readable, never corrupts with software version changes, and works across a wide array of software and systems.

### Basic Syntax

Learn Markdown basics in under five minutes. Use [markdownlivepreview.com](https://markdownlivepreview.com/) to practice.

~~~markdown
# Heading 1 (Your Chapter Title)

## Heading 2 (A Major Section)

This is a regular paragraph. You can make text **bold** or
*italic* easily.

* This is a bulleted list item
* And another one

1. This is a numbered list
2. And another one

Hyperlinks are [bounded by square brackets](https://bristol.ac.uk)

Include inline code with tickmarks such as `print("Hello World")`.

You can also display full code blocks:

```python
def add_numbers(a, b):
    return a + b
```

Images can be displayed as follows:

![Alt text describing the image for accessibility](path/to/image.png)

You must make sure that your image paths are relative to
the Markdown document.
~~~

### Editing Software

Markdown is plain text, so any editor works. Dedicated Markdown editors help:

- **Online:** [markdownlivepreview.com](https://markdownlivepreview.com/), [stackedit.io](https://stackedit.io/), [HackMD](https://hackmd.io), [GitHub's web editor](https://github.dev)
- **Desktop:** [Obsidian](https://obsidian.md/), [VS Code](https://code.visualstudio.com/) (recommended for programmers)

### "Flavours"

Standard Markdown is intentionally simple. Different communities built "flavours" to extend it. This can result in slightly confusing situations where different editors, environments, or tools can support different features (such as super/subscripts, strikethrough, highlighting, etc.) in [different ways](https://gist.github.com/vimtaai/99f8c89e7d3d02a362117284684baa0f).

Some flavours are:

- **Python-Markdown / Kramdown** (MkDocs, Jekyll) — good for documnentation web pages, less suited to long-form academic writing and cross-referencing
- **[MyST](https://mystmd.org/)** (JupyterBook) — richest for academic writing. Supports citations, numbered figures, equations, theorem environments
- **[Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown)** (Quarto) — similarly capable, preferred in the R community. Can export to Word, PDF, LaTeX

!!! note "Extensions"

    For instance, this very page is written in Markdown, but the MkDocs Material theme (which builds the website) supports a markdown extension called `admonitions`. That allows us to produce these neat little note boxes.

These was produced as follows - but they won't display correctly in 'vanilla' Markdown!

~~~text
!!! note "Extensions"

For instance, this very page is written in Markdown...
~~~

## 2: Writing with Jupyter Notebooks

Markdown is perfect for prose. But research involves code, data analysis, modelling, and plots—where Jupyter Notebooks shine. If you are interested in this sort of thing, you are likely already familiar with Jupyter Notebooks - especially Python users (although Jupyter also supports languages like R and Julia).

You can publish existing `.ipynb` files directly as web pages with rendered outputs. [This page](https://edu-notebooks.oggm.org/oggm-edu/glacier_water_resources.html) is an example of what that can look like.

### Quick Guide

To create and run notebooks locally, install the Jupyter ecosystem. If you already have Python configured, you can install it alongside in your local environment:

```bash
conda install jupyterlab

```

Once installed, spin up your authoring interface using this command:

```bash
jupyter lab

```

This launches a dashboard in your web browser where you can create and write Notebooks. Jupyter Notebooks combine computational code cells (running Python, R, or Julia) with explanatory narrative text cells (written in Markdown). Instructions on how to take advantage of this full functionality are best left to other tutorials.

### Intersecting with Other Tools (The Static Site Landscape)

As you explore hosting static academic sites, you will hear about several competing tools. Here is how Jupyter Notebooks interact with them:

| Tool Ecosystem | Notebook Intersection | Best Used For |
| --- | --- | --- |
| **JupyterBook 2 / MyST** | **Native Integration.** Built explicitly to execute and render `.ipynb` files perfectly out of the box without any translation plugins. | Computational books, interactive lecture notes, and reproducible research websites. |
| **MkDocs** | **Requires Plugins.** MkDocs is incredibly fast and designed for software documentation. It natively only reads Markdown; to use notebooks, you must install third-party extensions like `mkdocs-jupyter`. | Software documentation and clean, code-light reference manuals. |
| **Jekyll** | **Requires Exporting.** Jekyll is the classic Ruby-based engine powering standard GitHub Pages. It has no understanding of computational code blocks. To use notebooks, you have to manually export them to Markdown or HTML first using `nbconvert`. | Traditional blogs, static department homepages, or text-only portfolios. |

**The Takeaway for the Workshop:** If your academic project contains active code cells and data visualizations that need to be generated dynamically from source files, **JupyterBook 2** is engineered precisely to handle that heavy lifting without requiring clumsy add-ons or manual file conversions.
