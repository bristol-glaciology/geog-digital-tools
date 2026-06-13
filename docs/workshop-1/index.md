# Workshop 1: Open-source tools for outreach, teaching and research documentation

Researchers and teachers often want to share their work online — whether that's a personal website, class notes, a book or project documentation — but don't know where to start.

This workshop introduces simple, free tools that make it easy to build professional-looking websites, with no web development experience required. The workshop is not meant to be a comprehensive class on web design, but is rather an opinionated introduction to tools we (and others!) use a lot, with demos and some hands-on time.

!!! tip "Registration / logistics"

    - When: **19 June 2026**
    - Where: **Hepple, School of Geographical Sciences, University of Bristol**
    - How: **Please register by filling [this MS form](https://forms.office.com/e/sSfxgz3efs) so we can plan accordingly!**

    | Time  |                                                     |
    |-------|-----------------------------------------------------|
    | 12:30 | Arrival and lunch (provided)                        |
    | 13:30 | **Part 1** — Static websites                        |
    | 15:00 | Coffee break                                        |
    | 15:20 | **Part 2** — Lightning talks                        |
    | 15:40 | **Part 3** — Hands-on & discussion                  |
    | 16:30 | Workshop ends                                       |
    | 17:00 | Optional pub visit — School Gemini Drinks           |

---

## You should come if ...

... you're interested in creating any of these:

- [Personal websites](https://trchudley.github.io)
- [Research group websites](https://bristol-glaciology.github.io/)
- [Class notes](https://fabienmaussion.info/climate_risks) or [online textbooks](https://trchudley.github.io/geospatial-python-glaciology/).
- [Tutorials](https://tutorials.oggm.org) or [software documentation](https://pdemtools.readthedocs.io)
- [Educational platforms](https://edu.oggm.org)
- and more!

We expect the workshop to be most beneficial for PGRs and ECRs, but everyone is very welcome to join!

---

## Programme

### Part 1 — Static websites (13:30–15:00)

The purpose of part 1 is to provide a general overview of a family of tools which are all very similar in concept (turning written content and images into websites), and to help you choose the right tool for your needs.

1. [A quick intro to static site generators](intro-static-sites.md)
2. [Writing content: Markdown and Notebooks](markdown-and-notebooks.md)
3. Turning content into websites:
    - [JupyterBook / MyST](jupyterbook.md) — good for educational / computational content, tutorials, papers, books
    - [MkDocs & Material](mkdocs.md) — good for software documentation and project websites like this one
    - [Jekyll](jekyll.md) — good for fancier personal or project websites
    - Honourable mention: [Sphinx](sphinx.md) — the venerable and still well-used software documentation tool
4. [Hosting: GitHub Pages and ReadTheDocs](hosting.md), web analytics (brief overview).
5. [Git and GitHub — the basics](git-intro.md) — what is version control and why you need it to publish on GitHub.

*The links above point to the reference pages for each topic — they reflect the structure of the slides and are intended for use during the hands-on session and after the workshop.*

*Coffee break (15:00–15:20)*

### Part 2 — Lightning talks (15:20–15:40)

5 minutes (or less!) showcases from the participants:

- Kara Lamantia: An Open Source Tool for Mapping Key Metrics of Glacier Health from Space
- Tom Chudley: Data distribution GUIs on zero budget
- Fabien Maussion: Interactive applications to learn and teach about glaciers
- Fabien Maussion: OGGM-Hub and OGGM-Classroom — glacier modelling "on the cloud"

### Part 3 — Hands-on & discussion (15:40–16:30)

This session is unstructured — use it however is most useful to you.

- **Discussion table** — bring your ideas and questions. What would you like to build? A personal website, a teaching platform, project documentation? We can help you figure out which tool fits and where to start. This is also a good moment to discuss what a shared teaching website for the group could look like.
- **Hands-on** — start building your own site with help from Tom and Fabien. Bring your laptop and, if you have one, a use case (a paper, dataset, or course you'd like to put online). See the [hands-on tutorial](hands-on.md) for the available paths (Jekyll, MkDocs, JupyterBook).
- **Feel free to leave** at any point if you have what you need!

---

## How to prepare (optional)

**Before the workshop:**

- :material-lightning-bolt: **Register a lightning talk** via the form if you have a tool or workflow you'd like to highlight — 5 minutes is plenty.
- :material-laptop: **[Install Conda or Mamba](installation.md)** if you plan to use MkDocs or JupyterBook on the day — both require Python. If you are going the Jekyll route, no installation is needed: the hands-on tutorial works entirely through the GitHub web interface.

**On the day:**

- :material-folder-open: **Bring a use case** — a paper, dataset, course, or codebase you'd like to put online. It helps us figure out which tool fits your needs and get you started on the spot.
- :material-forum: **Bring your questions and opinions** — the discussion roundtable is for everyone.
