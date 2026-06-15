# 3.2 JupyterBook & MyST

[JupyterBook](https://jupyterbook.org/) is a documentation engine specifically tailored to technical and scientific content — code documentation, textbooks, or lecture notes. As the name suggests, it is particularly useful for translating `.ipynb` Jupyter Notebook documents into web pages with no effort on the part of the user. It also accepts LaTeX `.tex` files, and can export your content to a `.pdf` as well as a website.

As with most examples here, the [JupyterBook website itself](https://jupyterbook.org/) is the primary example of a JupyterBook site, but other examples include [maths-heavy online textbooks](https://notes.eecs245.org/), [online supporting content for written GeoAI textbooks](https://book.opengeoai.org/), or [online working groups for the geoscience community](https://projectpythia.org/).

!!! note "Jupyter Book v1 (Sphinx) vs v2 (MyST)"

    [Jupyter Book v2](https://jupyterbook.org/) was released in November 2025. Prior to this [Jupyter Book v1](https://jupyterbook.org/v1/intro.html) was the default. v1 was based around [the Sphinx documentation tool](workshop-1/sphinx). v2 is based around the [MyST](https://mystmd.org/) (Markedly Structured Text) engine (in fact, the two are [basically the same thing](https://jupyterbook.org/community/ecosystem/)). 
    
    Ultimately, the underlying rendering engine is something the user rarely needs to think about. The only reason to keep the move to v2/MyST in mind is that many online tutorials (and hallucinatory LLM output!) will still be referencing Sphinx-style setup and language. There is, in our opinion, [no reason to learn v1/Sphinx at this point](sphinx.md) (although, if you have a project already using it, there is also no compelling reason to move away from it).

## Getting Started with JupyterBook

The [JupyterBook documentation](https://jupyterbook.org/stable/get-started/) is very good, but we outline a streamlined version of the workflow is available here:

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