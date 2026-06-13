# 1. A quick intro to static site generators

## What is a "static" website?

When you visit a website, your browser receives HTML, CSS, and JavaScript files and renders them into the page you see. The question is: *when* are those files created?

A **dynamic** website — think WordPress, university intranet portals, or online banking — generates each page *on demand*, the moment someone visits. A server runs code, queries a database, assembles the HTML, and sends it back. This is powerful but comes with a cost: you need a running server, a database, regular security updates, and something to go wrong at 2am before a grant deadline.

A **static** website is the opposite: all the HTML files are pre-built *in advance* and simply served as-is when someone visits. There is no server-side processing, no database, nothing to maintain. The page for this workshop was built on a laptop, uploaded to GitHub, and is now served for free from their servers to anyone in the world.

The trade-off is interactivity: static sites cannot, by default, do things like user logins, dynamic search, or live data feeds. For most academic use cases — course notes, documentation, personal websites, project pages — this is not a limitation at all.

## Static site *generators*

Writing HTML by hand is tedious. A **static site generator** lets you write content in a human-friendly format (usually [Markdown](markdown-and-notebooks.md) or Jupyter Notebooks) and takes care of converting it into a full website — navigation, styling, search, and all.

The landscape of static site generators is large. [StaticGen](https://jamstack.org/generators/) lists hundreds of them. They differ in their programming language, templating system, built-in features, and the kind of content they are designed for. The good news is that they all share the same core idea, so switching between them is not as daunting as it sounds.

## What is *not* a static site generator?

Before getting into static site generators, it is worth acknowledging the alternatives — because some academics already use one of them:

- **WordPress** — the most widely used website platform in the world. Powers a huge number of university department and research group pages. Powerful and flexible, but requires paid hosting, regular maintenance and security updates, and a certain amount of ongoing IT overhead. Content is locked in a database, not in plain text files you can easily control.
- **University or institutional CMS** — many universities provide a content management system for staff pages. Easy to get started, but typically very limited in customisation, slow to update, and not portable if you move institutions.
- **Drag-and-drop builders (Wix, Squarespace, Google Sites)** — low barrier to entry and polished templates, but usually cost money, lock your content into a proprietary platform, and offer little control over structure or automation.
- **Hiring a web developer** — a perfectly reasonable option for a large, funded project, but expensive and creates a dependency: every update goes through someone else.

Static site generators occupy a different niche: free, portable, version-controlled, and requiring no ongoing maintenance — at the cost of a small initial learning curve. For individual researchers, small groups, or anyone who already works with plain text files and version control, they are often the better fit.

## The tools we cover today

Rather than a survey, this workshop focuses on a small, opinionated selection of tools that we and our colleagues actually use. Here is a quick overview:

| Tool | Best for | Why not always? | Examples |
| --- | --- | --- | --- |
| [JupyterBook / MyST](jupyterbook.md) | Sites built around Jupyter Notebooks and computational content: lecture notes, tutorials, papers with code | Overkill if you don't need notebook execution. Consider [Quarto](https://quarto.org) if you work primarily in R or want a single tool for documents, slides, and websites. | • [OGGM tutorials](https://tutorials.oggm.org)<br>• [Geospatial Python for Glaciology](https://trchudley.github.io/geospatial-python-glaciology/)<br>• [Climate Risks practicals](https://fabienmaussion.info/climate_risks)<br>• [The Turing Way](https://book.the-turing-way.org/) |
| [MkDocs & Material](mkdocs.md) | Clean, fast documentation and project websites; easy to set up and maintain | Less design flexibility than Jekyll for highly customised layouts. | • [This site](https://bristol-glaciology.github.io/geog-digital-tools/)<br>• [IGM Model](https://igm-model.org)<br>• [RGI](https://rgidata.org/) |
| [Jekyll](jekyll.md) | Personal and group websites where design and layout matter; blog-style content | More setup friction; requires Ruby. [Hugo](https://gohugo.io) is a popular alternative with a faster build system. | • [Fabien's site](https://fabienmaussion.info)<br>• [Tom's site](https://trchudley.github.io)<br>• [Bristol Glaciology](https://bristol-glaciology.github.io/) |
| [Sphinx](sphinx.md) *(honourable mention)* | The long-standing standard for Python package documentation | Complex configuration, dated defaults — largely superseded for new projects by [MkDocs](mkdocs.md) and [JupyterBook](jupyterbook.md). Worth knowing because you will encounter it everywhere. | • [OGGM](https://docs.oggm.org)<br>• [xarray](https://docs.xarray.dev)<br>• [pDEMtools](https://pdemtools.readthedocs.io) |

!!! tip "Which one should I use?"

    - You work with code and want to publish notebooks as a tutorial, course, or paper → **JupyterBook**
    - You're writing a book or long document with lots of cross-references, citations, or equations (even without code) → **JupyterBook** (MyST has excellent support for all of these)
    - You're documenting a software project or tool → **MkDocs**
    - You want a website to document project outcomes, data, or fieldwork → **MkDocs**
    - You want a personal or research group website → **Jekyll** or **MkDocs**
    - You want a blog or news feed → **Jekyll** or **MkDocs** (both support it)
    - You maintain a Python package → **Sphinx** (but MkDocs is increasingly popular here too)

All four tools are free and open-source. All of them produce websites that can be hosted for free on [GitHub Pages](https://pages.github.com/) or [ReadTheDocs](https://about.readthedocs.com). None of them require any web development experience to get started.
