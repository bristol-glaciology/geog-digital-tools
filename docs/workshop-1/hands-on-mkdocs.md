# A minimal workflow to create a MkDocs site hosted by GitHub pages.

!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and Jekyll/Minimal Mistakes, but full documentation is also available online:
   
    - [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
    - [GitHub Pages](https://docs.github.com/en/pages)


This page shows how to quickly create an example website using [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme, based on a template available on the [`bristol-glaciology` Github repository](https://github.com/bristol-glaciology/example-mkdocs-website). You can [view a preview of what the website looks like](https://bristol-glaciology.github.io/example-mkdocs-website/).

!!! warning "Basic git knowledge required"

    This tutorial requires a GitHub account and a working knowledge of how to interact with `git` and GitHub repos. If you are less experienced with these workflows, you may wish to explore the [introductory documentation](https://docs.github.com/en/get-started/start-your-journey/hello-world) or work with [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) as a GUI-only alternative. For today, the [Jekyll personal website guide](hands-on-jekyll.md) can be done through the GitHub web GUI and does not require any `git` or command-line interactions.

## Getting the website

### Forking the repository

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
conda install -r mkdocs mkdocs-material mkdocs-jupyter
```

## Editing

### The config file: `mkdocs.yml`

The `mkdocs.yml` file is the primary config file. Go through it and edit the settings to your own taste - these should be self-explanatory, but you can find out more [in the material docs](https://squidfunk.github.io/mkdocs-material/creating-your-site/).

### Add pages and assets

Add content (markdown files, jupyter notebook, and image assets) insite of the `./docs` directory:

- `docs/` - Documentation pages
  - `index.md` - Home page
  - `docs/pages/` - Additional pages
  - `docs/assets/` - Images and other assets

To ensure that these are appropriately arranged within the site and navbar, be sure to properly edit the `nav` section of `mkdocs.yml`. 

## Building and Pushing

### Running Locally

To build and serve the site locally:

```bash
mkdocs serve
```

The site will be available at `http://localhost:8000`

### Building for Production

You don't need this step if you are planning to deploy to GitHub Pages. However, if you otherwise need a static copy of the site (i.e. a raw bundle of `html` files), you can build the site for production using:

```bash
mkdocs build
```
The output will be in the `site/` directory.


### Publishing

To deploy to GitHub Pages:

```bash
mkdocs gh-deploy
```

When you do this, a new `gh-deploy` branch should be set up (you will never need to touch this manually), and your repository should be configured correctly to initialise it at `<my-username>.github.io/<my-repository-name>`. You can check this by going to `Settings > Pages`: you should see that the site is set up to `Deploy from a branch`, and that branch is `gh-pages`. 