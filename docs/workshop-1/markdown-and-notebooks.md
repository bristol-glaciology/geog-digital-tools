# 2. Writing content: Markdown and Notebooks

The static website generators explored in this workshop are designed to create pages from very basic document building blocks: namely [Markdown](https://www.markdownguide.org/) for text documents (as well as images, tables, etc.) and [Jupyter Notebooks](https://jupyter.org/) for code.

We will break this down into two halves: writing pure text using Markdown, and managing code workflows with Jupyter Notebooks.

## 1: Writing with Markdown

If you have ever formatted a text file or written a `README` file on GitHub, you have likely already encountered Markdown.

Markdown is a lightweight, human-readable "markup language" created in 2004. Unlike Microsoft Word (`.docx`), which hides complex XML styling code under the hood, Markdown files are just plain text identical to any `.txt` file, just with a different file extension (`.md`) to communicate that Markdown is being used.

Unlike more complex marksup languages (e.g. XML, HTML, LaTeX, etc...) Markdown is designed to be very easy-to-read. You use simple text characters to indicate semantic structure (like using `#` for a heading or `**bold text**` for bold text).

Because it is plain text, Markdown files open instantly, never become corrupted due to software version changes, and work seamlessly a wide array of software and systems.

### Basic Syntax

The beauty of Markdown is that you can learn the basics in under five minutes. The best way to do this is to play around yourself using an online editor such as [markdownlivepreview.com](https://markdownlivepreview.com/), but some basic introductions are below. Paste them into a Markdown editor to see how they are visualised!

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

```markdown
def add_numbers(a, b):
    return a + b
```

Images can be displayed as follows:

![Alt text describing the image for accessibility](path/to/image.png)

You must make sure that your image paths are relative to
the Markdown document.
~~~

### Editing Software

Because Markdown is plain text, you can technically write it in any application - such as Notepad or TextEdit. However, a Markdown-specific editor can help you preview the documentation live. This can be online, such as the barebones [markdownlivepreview](https://markdownlivepreview.com/) or [stackedit.io](https://stackedit.io/app#), through to slightly more full-featured offerings such as [HackMD](https://hackmd.io) or [GitHub's web editor](https://github.dev).

There are also specialist Markdown desktop apps such as [Obdisian](https://obsidian.md/), but for those of you coming at this from a programming background, you might as well take advantage of the robust family of Markdown extension within the [VS Code IDE](https://code.visualstudio.com/) (the official recommended IDE of this workshop).

### "Flavours"

Standard Markdown is intentionally simple, which is also its primary limitation. Over time, different communities built "flavours" to extend what Markdown can do. This can result in slightly confusing situations where different editors, environments, or tools can support different features (such as super/subscripts, strikethrough, highlighting, etc.) in [different ways](https://gist.github.com/vimtaai/99f8c89e7d3d02a362117284684baa0f).

As a result, whilst 90% of what you want to do with Markdown will be achievable with the basic syntax, you should always try and be aware of what additional syntax might be supported when writing Markdown files for specific tools.

!!! note "Extensions"

    For instance, this very page is written in Markdown, but the MkDocs Material theme (which builds the website) supports a markdown extension called `admonitions`. That allows us to produce these neat little note boxes.

These was produced as follows - but they won't display correctly in 'vanilla' Markdown!

~~~text
!!! note "Extensions"

For instance, this very page is written in Markdown...
~~~

This is simultaneously a lesson and a warning...

### A note for book and paper writers

If you are thinking about writing something more structured — a textbook, a thesis chapter, a long report — standard Markdown will quickly feel limiting. The features academics need most (citations, numbered figures, cross-references, LaTeX equations) are not part of the base spec. Here is where the choice of flavour matters:

- **[MyST](https://mystmd.org/)** (used by JupyterBook) — the richest option for academic writing. Native support for citations via BibTeX, numbered and cross-referenced figures, equations, and theorem environments. Designed explicitly for scientific content.
- **[Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown)** (used by [Quarto](https://quarto.org)) — a similarly capable alternative, and the tool of choice in the R community. Pandoc can also convert your document to Word, PDF, or LaTeX if needed.
- **Python-Markdown / Kramdown** (MkDocs, Jekyll) — good for documentation and web pages, but less suited to long-form academic writing with heavy cross-referencing.

If citations and cross-references are central to what you want to build, **JupyterBook/MyST** or **Quarto** are the right starting points.

## 2: Writing with Jupyter Notebooks

While Markdown is perfect for prose, websites academics want to produce often involve code, data analysis, modelling, and plotting. This is where [Jupyter Notebooks](https://jupyter.org/) (`.ipynb`) can provide real value for including code and code outputs.

If you are interested in this sort of thing, you are likely already familiar with Jupyter Notebooks - especially Python users (although Jupyter also supports languages like R and Julia).

If you already work with Jupyter Notebooks, you don't need an introduction to running them — the key thing for this workshop is knowing that some static site tools can take your existing `.ipynb` files and turn them directly into web pages, complete with rendered outputs. [This page](https://edu-notebooks.oggm.org/oggm-edu/glacier_water_resources.html) is an example of what that can look like.

### Intersecting with Other Tools (The Static Site Landscape)

As you explore hosting static academic sites, you will hear about several competing tools. Here is how Jupyter Notebooks interact with them:

| Tool Ecosystem | Notebook Intersection | Best Used For |
| --- | --- | --- |
| **JupyterBook 2 / MyST** | **Native Integration.** Built explicitly to execute and render `.ipynb` files perfectly out of the box without any translation plugins. | Computational books, interactive lecture notes, and reproducible research websites. |
| **MkDocs** | **Requires Plugins.** MkDocs is incredibly fast and designed for software documentation. It natively only reads Markdown; to use notebooks, you must install third-party extensions like `mkdocs-jupyter`. | Software documentation and clean, code-light reference manuals. |
| **Jekyll** | **Requires Exporting.** Jekyll is the classic Ruby-based engine powering standard GitHub Pages. It has no understanding of computational code blocks. To use notebooks, you have to manually export them to Markdown or HTML first using `nbconvert`. | Traditional blogs, static department homepages, or text-only portfolios. |

**The Takeaway for the Workshop:** If your academic project contains active code cells and data visualizations that need to be generated dynamically from source files, **JupyterBook 2** is engineered precisely to handle that heavy lifting without requiring clumsy add-ons or manual file conversions.
