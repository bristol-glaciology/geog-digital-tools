# A minimal workflow to create a Jupyter Book site hosted by GitHub Pages

!!! note "External Documentation"

    Full documentation:
    - [Jupyter Book](https://jupyterbook.org/stable/get-started/)
    - [GitHub Pages](https://docs.github.com/en/pages)

This page shows how to create an example Jupyter Book site from a template on the [`bristol-glaciology` GitHub organisation](https://github.com/bristol-glaciology/example-jupyterbook-website). [See a preview here.](https://bristol-glaciology.github.io/example-jupyterbook-website/)

!!! warning "Basic git and Python knowledge recommended"

    This tutorial assumes a GitHub account and familiarity with `git` and GitHub repos. If you're less experienced, try the [GitHub docs introduction](https://docs.github.com/en/get-started/start-your-journey/hello-world) or [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop).
    
    For now, the [Jekyll guide](hands-on-jekyll.md) works entirely through the GitHub web GUI with no git or command line.

## Getting the website

!!! tip "No GitHub account? Download instead"

    You do not need a GitHub account to try Jupyter Book. On the [template repository](https://github.com/bristol-glaciology/example-jupyterbook-website), click the green **Code** button → **Download ZIP**, then unzip it on your computer. You can then follow the *Editing locally* steps below and preview your site.
    
    You only need an account if you later want to **publish** it online (the optional final step), in which case **fork** the website using the instructions below.

### Forking the website from GitHub

1. Navigate to the template repository:

    ```
    https://github.com/bristol-glaciology/example-jupyterbook-website
    ```

2. Click the **Fork** button in the top-right corner of the GitHub page.

3. Choose the GitHub account or organisation where you want to create the fork.

4. Configure the fork name:

   * If this will be your primary GitHub Pages site, rename the repository to:

     ```
     <your-github-username>.github.io
     ```

     For example, a user called `alice` naming the repo `alice.github.io` will have their site be published at `https://alice.github.io`

   * If this will be a project site instead, give the repository any suitable name. For example, a repo with the title `glacier-project` will be published at:

     ```
     https://<your-github-username>.github.io/glacier-project
     ```

5. Create the fork using the default options.

![Fork interface](img/fork.png)

**Remember to replace the text with** `https://<your-github-username>.github.io`

### Downloading the repository locally

1. Open your fork on GitHub
2. Click **Code** (green button)
3. Copy the repository URL (HTTPS or SSH)
4. In a terminal, navigate to where you want the project
5. Clone it:
    ```bash
    git clone https://github.com/<your-github-username>/<repository-name>.git
    ```
6. Move into the directory:
    ```bash
    cd <repository-name>
    ```

## Editing locally

### Installation

Install dependencies in your Python environment:

```bash
conda create --name webdev
conda activate webdev
conda install -c conda-forge jupyter-book>=2.0.0 jupyter jupyterlab matplotlib numpy ghp-import
```

## Editing

### The config file: `myst.yml`

Open the newly generated `myst.yml` file in a text editor. This single file controls everything. Fill out your global project variables under the `project:` block (such as `title`, `description`, and `authors`).

### Add pages and assets

Create files directly in your project directory. Jupyter Book supports [Markdown (`.md`), Jupyter Notebooks (`.ipynb`), and LaTeX (`.tex`)](https://jupyterbook.org/stable/authoring/file-types/). [MyST-style Markdown](https://jupyterbook.org/stable/authoring/mystmd/) adds support for equations, citations, and more.

Organize content in folders as your project grows and keep images in a dedicated assets directory.

Edit the `toc:` section in `myst.yml` to define structure, titles, and nested sections.

```yaml
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
```


## Building and Pushing

### Running Locally

Launch the built-in development server to view the site on your computer. It creates a local web server that automatically live-updates in your browser whenever you modify a file:

```bash
jupyter book start
```

JupyterBook will report the URL at which it can be found (e.g. `http://localhost:3000`).

### Export a PDF

To generate a print copy for class notes or textbooks:

```bash
jupyter book build --pdf
```

### Publish to GitHub Pages (optional, requires a GitHub account)

Deploy to GitHub Pages:

```bash
jupyter book init --gh-pages
```

Answer the prompted questions; this will create a `.github/workflows/deploy.yml` file. 

Commit everything to a public GitHub repository, enable **Pages** in the repository settings set to build via **GitHub Actions**, and your site will be published automatically upon new push actions. You can check whether deployment has worked within the GitHub Actions tab.