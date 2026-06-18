# A minimal workflow to create a MkDocs site hosted by GitHub pages.

!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and MkDocs Material, but full documentation is also available online:
   
    - [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
    - [GitHub Pages](https://docs.github.com/en/pages)


This page shows how to quickly create an example website using [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme, based on a template available on the [`bristol-glaciology` Github repository](https://github.com/bristol-glaciology/example-mkdocs-website). You can [view a preview of what the website looks like](https://bristol-glaciology.github.io/example-mkdocs-website/).

!!! warning "Basic git and Python knowledge required"

    This tutorial recommends a GitHub account and a working knowledge of how to interact with `git` and GitHub repos. If you are less experienced with these workflows, you may wish to explore the [introductory documentation](https://docs.github.com/en/get-started/start-your-journey/hello-world) or work with [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) as a GUI-only alternative. For today, the [Jekyll personal website guide](hands-on-jekyll.md) can be done through the GitHub web GUI and does not require any `git` or command-line interactions.

    You will also need to know how to setup a Python environment, but you do not need to know how to code in Python.

## Getting the website

!!! tip "No GitHub account? Download instead"

    You do not need a GitHub account to try MkDocs. On the [template repository](https://github.com/bristol-glaciology/example-mkdocs-website), click the green **Code** button → **Download ZIP**, then unzip it on your computer. You can then follow the *Editing locally* steps below and preview your site. You only need an account if you later want to **publish** it online (the optional final step), in which case use the **fork** route instead.

### Forking the website from GitHub

1. Navigate to the template repository:

    ```
    https://github.com/bristol-glaciology/example-mkdocs-website
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

### Installation

Ensure the necessary dependencies are installed within your chosen Python environment:

```bash
conda create --name webdev
conda activate webdev
conda install -c conda-forge mkdocs-material mkdocs-jupyter
```

## Editing

### The config file: `mkdocs.yml`

The `mkdocs.yml` file is the primary config file. Go through it and edit the settings to your own taste - these should be self-explanatory, but you can find out more [in the material docs](https://squidfunk.github.io/mkdocs-material/creating-your-site/).

### Add pages and assets

Add content (markdown files, jupyter notebook, and image assets) inside the `./docs` directory:

- `docs/` - Documentation pages
  - `index.md` - Home page
  - `docs/pages/` - Additional pages
  - `docs/assets/` - Images and other assets

Edit the `nav` section of `mkdocs.yml` to ensure that these are appropriately arranged within the site and navbar.

## Building and Pushing

### Running Locally

To build and serve the site locally:

```bash
mkdocs serve --livereload
```

The site will be available at `http://localhost:8000`

### Building for Production

You don't need this step if you are planning to deploy to GitHub Pages. However, if you otherwise need a static copy of the site (i.e. a raw bundle of `html` files), you can build the site for production using:

```bash
mkdocs build
```
The output will be in the `site/` directory.


### Publishing (optional, requires a GitHub account)

Publishing your site online requires a GitHub account: you must have **forked** the template (rather than downloaded the ZIP) so that you have a repository to deploy from.

To deploy to GitHub Pages:

```bash
mkdocs gh-deploy
```

When you do this, a new `gh-deploy` branch should be set up (you will never need to touch this manually), and your repository should be configured correctly to initialise it at `<my-username>.github.io/<my-repository-name>`. You can check this by going to `Settings > Pages`: you should see that the site is set up to `Deploy from a branch`, and that branch is `gh-pages`. 