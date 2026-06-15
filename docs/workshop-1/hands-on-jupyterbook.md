# A minimal workflow to create a Jupyter Book site hosted by GitHub pages.


!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and Jekyll/Minimal Mistakes, but full documentation is also available online:
   
    - [Jupyter Book](https://jupyterbook.org/stable/get-started/)
    - [GitHub Pages](https://docs.github.com/en/pages)

This page shows how to quickly create an example website using [Jupyter Book](https://jupyterbook.org/) with the [MyST engine](https://mystmd.org/), based on a template available on the [`bristol-glaciology` Github repository](https://github.com/bristol-glaciology/example-jupyterbook-website). You can [view a preview of what the website looks like](https://bristol-glaciology.github.io/example-jupyterbook-website/).

!!! warning "Basic git knowledge required"

    This tutorial requires a GitHub account and a working knowledge of how to interact with `git` and GitHub repos. If you are less experienced with these workflows, you may wish to explore the [introductory documentation](https://docs.github.com/en/get-started/start-your-journey/hello-world) or work with [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) as a GUI-only alternative. For today, the [Jekyll personal website guide](hands-on-jekyll.md) can be done through the GitHub web GUI and does not require any `git` or command-line interactions.

## Getting the website

### Forking the repository

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

1. Create the fork.

### Downloading the repository locally

Once the fork has been created, you need a local copy on your computer.

1. Open your fork on GitHub.

2. Click the green **Code** button.

3. Copy the repository URL (HTTPS or SSH).

4. Open a terminal and navigate to the directory where you want to store the project.

5. Clone the repository:

    ```bash
    git clone https://github.com/<your-github-username>/<repository-name>.git
    ```

6. Move into the project directory:

    ```bash
    cd <repository-name>
    ```

## Editing locally

## Installation

Ensure the necessary dependencies are installed within your chosen Python environment:

```bash
conda create --name webdev
conda activate webdev
conda install -r python jupyter-book>=2.0.0 jupyter jupyterlab matplotlib numpy ghp-import
```

## Editing

### 3. The config file: `myst.yml`

Open the newly generated `myst.yml` file in a text editor. This single file controls everything. Fill out your global project variables under the `project:` block (such as `title`, `description`, and `authors`).

### Add pages and assets

Create files directly in your project directory. JupyterBook [natively supports](https://jupyterbook.org/stable/authoring/file-types/) regular Markdown (`.md`), Jupyter Notebooks (`.ipynb`), and LaTeX (`.tex`). [MyST-style Markdown](https://jupyterbook.org/stable/authoring/mystmd/) adds further capability, including native support for [LaTeX-style mathematical equations](https://jupyterbook.org/stable/authoring/math/). As your project grows, organise content into folders and keep images in a dedicated assets directory.

To organise the structure, you can edit the table of contents in your `myst.yml` file. Use the `toc:` section to define the structure, titles, and nested sections:

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


## Building and Pushing

### Running Locally

Launch the built-in development server to view the site on your computer. It creates a local web server that automatically live-updates in your browser whenever you modify a file:

~~~bash
jupyter book start
~~~

JupyterBook will report the URL at which it can be found (e.g. `http://localhost:3000`).

### Export a PDF

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