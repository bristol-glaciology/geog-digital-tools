# 3.2 JupyterBook & MyST

[JupyterBook](https://jupyterbook.org/) is a documentation engine for technical and scientific content—code documentation, textbooks, lecture notes. It converts Jupyter Notebooks (`.ipynb`) directly to web pages, and also supports LaTeX (`.tex`) files. You can export content to PDF or website.

Examples:
- [JupyterBook's own site](https://jupyterbook.org/)
- [math-heavy textbooks](https://notes.eecs245.org/)
- [GeoAI textbooks](https://book.opengeoai.org/)
- [geoscience working groups](https://projectpythia.org/).

!!! note "Jupyter Book v1 (Sphinx) vs v2 (MyST)"

    [Jupyter Book v2](https://jupyterbook.org/) was released in November 2025. Prior to this [Jupyter Book v1](https://jupyterbook.org/v1/intro.html) was the default. v1 was based around [the Sphinx documentation tool](workshop-1/sphinx). v2 is based around the [MyST](https://mystmd.org/) (Markedly Structured Text) engine (in fact, the two are [basically the same thing](https://jupyterbook.org/community/ecosystem/)). 
    
    For users, the underlying engine rarely matters. Many online tutorials (and hallucinatory LLMs) still reference Sphinx (v1), but there is [no reason to learn v1 now](sphinx.md). If you have an existing v1 project, stay with it.

## Getting Started with JupyterBook

The [official JupyterBook documentation](https://jupyterbook.org/stable/get-started/) is excellent. Here's a streamlined workflow:

### 1. Install JupyterBook

Requires Python. Install the core packages using `pip` or `conda`:

~~~bash
conda install jupyter-book>=2.0.0
~~~

### 2. Initialise a project

Create a new directory for your project, navigate to it in the command line, and initialise your workspace:

~~~bash
jupyter book init
~~~

### 3. Edit the `myst.yml` file

Open the newly generated `myst.yml` file in a text editor. This single file controls everything. Fill out your global project variables under the `project:` block (such as `title`, `description`, and `authors`).

### 4. Add content

Create files directly in your project directory. JupyterBook [natively supports](https://jupyterbook.org/stable/authoring/file-types/) regular Markdown (`.md`), Jupyter Notebooks (`.ipynb`), and LaTeX (`.tex`). [MyST-style Markdown](https://jupyterbook.org/stable/authoring/mystmd/) adds further capability, including native support for [LaTeX-style mathematical equations](https://jupyterbook.org/stable/authoring/math/). As your project grows, organise content into folders and keep images in a dedicated assets directory.

### 5. Configure the table of contents

Open your `myst.yml` file again. Use the `toc:` section to define the structure, titles, and nested sections:

~~~yaml
project:
  toc:
    - file: docs/index.md
    - title: Part I - Foundations
      children:
        - file: docs/part1/intro.md
        - file: docs/part1/basics.md
    - title: Part II - Advanced
      children:
        - file: docs/part2/advanced.md
~~~

### 6. Build and preview locally

Launch the built-in development server to view the site on your computer. It creates a local web server that automatically live-updates in your browser whenever you modify a file:

~~~bash
jupyter book start
~~~

JupyterBook will report the URL at which it can be found (e.g. `http://localhost:3000`).

### 7. Export a PDF

To generate a print copy (for class notes or textbooks):

~~~bash
jupyter book build --pdf
~~~

### 8. Publish to GitHub Pages

JupyterBook has a built-in function to set up GitHub Pages deployment:

~~~bash
jupyter book init --gh-pages
~~~

Answer the prompted questions; this will create a `.github/workflows/deploy.yml` file. 

Commit everything to a public GitHub repository, enable **Pages** in the repository settings set to build via **GitHub Actions**, and your site will be published automatically upon new push actions. You can check whether deployment has worked within the GitHub Actions tab.