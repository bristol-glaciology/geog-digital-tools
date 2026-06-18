# 1. A quick intro to static site generators

## What is a "static" website?

Your browser generates HTML, CSS, and JavaScript to render pages when you visit a website. The question is: *when* does this happen?

**Dynamic** websites generate each page on demand (WordPress, university portals, online banking). A server runs code, queries a database, and sends back HTML. This is powerful but requires maintenance: running servers, databases, security updates, and something will still go wrong at 2am before a grant deadline.

**Static** websites build all HTML *in advance* and serve it as-is. No server-side processing, no database, nothing to maintain. The page for this workshop was built on a laptop, uploaded to GitHub, and is now served for free from their servers to anyone in the world.

The trade-off: static sites can't do logins, dynamic search, or live data feeds. For most academic use (course notes, documentation, personal pages, project sites) this is not a limitation.

## Static site *generators*

Writing HTML by hand is tedious. A **static site generator** converts your content (usually [Markdown](markdown-and-notebooks.md) or Jupyter Notebooks) into a complete website with navigation, styling, search, and all.

Hundreds of static site generators exist (see [StaticGen](https://jamstack.org/generators/)), differing in language, templating, built-in features, and content type. The good news is that they all share the same core idea, so switching between them is straightforward.

## What is *not* a static site generator?

Other platforms exist:

- **WordPress** — the most widely used website platform in the world. Powers a huge number of university department and research group pages. Powerful and flexible, but requires paid hosting, regular maintenance and security updates, and a certain amount of ongoing IT overhead. Content is locked in a database, not in plain text files you can easily control.
- **University or institutional CMS** — many universities provide a content management system for staff pages. Easy to get started, but typically very limited in customisation, slow to update, and not portable if you move institutions.
- **Drag-and-drop builders (Wix, Squarespace, Google Sites)** — low barrier to entry and polished templates, but usually cost money, lock your content into a proprietary platform, and offer little control over structure or automation.
- **Hiring a web developer** — a perfectly reasonable option for a large, funded project, but expensive and creates a dependency: every update goes through someone else.

Static site generators fit a different niche: free, portable, version-controlled, maintenance-free—at the cost of a small learning curve. For individual researchers, small groups, or anyone who already works with plain text and version control, they're often the better choice.

## The tools we cover today

Rather than a survey, this workshop focuses on a small, opinionated selection of tools that we and our colleagues actually use. Here is a quick overview:

| Tool | Best for | Why not always? | Examples |
| --- | --- | --- | --- |
| [JupyterBook / MyST](jupyterbook.md) | Sites built around Jupyter Notebooks and computational content: lecture notes, tutorials, papers with code | Overkill if you don't need notebook execution. Consider [Quarto](https://quarto.org) if you work primarily in R or want a single tool for documents, slides, and websites. | • [OGGM tutorials](https://tutorials.oggm.org)<br>• [Geospatial Python for Glaciology](https://trchudley.github.io/geospatial-python-glaciology/)<br>• [Climate Risks practicals](https://fabienmaussion.info/climate_risks)<br>• [The Turing Way](https://book.the-turing-way.org/) |
| [MkDocs & Material](mkdocs.md) | Clean, fast documentation and project websites; easy to set up and maintain | Less design flexibility than Jekyll for highly customised layouts. | • [This site](https://bristol-glaciology.github.io/geog-digital-tools/)<br>• [IGM Model](https://igm-model.org)<br>• [RGI](https://rgidata.org/) |
| [Jekyll](jekyll.md) | Personal and group websites where design and layout matter; blog-style content | More setup friction; requires Ruby. [Hugo](https://gohugo.io) is a popular alternative with a faster build system. | • [Fabien's site](https://fabienmaussion.info)<br>• [Tom's site](https://trchudley.github.io)<br>• [Bristol Glaciology](https://bristol-glaciology.github.io/) |
| [Sphinx](sphinx.md) *(honourable mention)* | The long-standing standard for Python package documentation, and used in [Jupyter Book v1](https://jupyterbook.org/v1/intro.html) | Complex configuration, dated defaults — largely superseded for new projects by [MkDocs](mkdocs.md) and [JupyterBook v2](jupyterbook.md) / [MyST](https://mystmd.org/). Worth knowing because you will encounter it everywhere. | • [OGGM](https://docs.oggm.org)<br>• [xarray](https://docs.xarray.dev)<br>• [pDEMtools](https://pdemtools.readthedocs.io) |

!!! tip "Which one should I use?"

    - You work with code and want to publish notebooks as a tutorial, course, or paper → **JupyterBook**
    - You're writing a book or long document with lots of cross-references, citations, or equations (even without code) → **JupyterBook** (MyST has excellent support for all of these)
    - You're documenting a software project or tool → **MkDocs**
    - You want a website to document project outcomes, data, or fieldwork → **MkDocs**
    - You want a personal or research group website → **Jekyll** or **MkDocs**
    - You want a blog or news feed → **Jekyll** or **MkDocs** (both support it)
    - You maintain a Python package → **Sphinx** (but MkDocs is increasingly popular here too)

All four tools are free and open-source. All of them produce websites that can be hosted for free on [GitHub Pages](https://pages.github.com/) or [ReadTheDocs](https://about.readthedocs.com). None of them require any web development experience to get started.
