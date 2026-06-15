# A minimal workflow to create a Jekyll site hosted by Github pages

!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and Jekyll/Minimal Mistakes, but full documentation is also available online:
   
    - [GitHub Pages](https://docs.github.com/en/pages)
    - [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)

## Introduction

The easiest and free way to host static sites is by taking advantage of the [GitHub Pages](https://docs.github.com/en/pages) feature of GitHub.

!!! note "Alternative Options"

    You can also host on [ReadTheDocs](https://docs.readthedocs.com/), which is particularly popular for Python package documentation (see instructions for [MkDocs](https://docs.readthedocs.com/platform/stable/intro/mkdocs.html) and [MyST/Jupyter Book](https://mystmd.org/guide/deployment-readthedocs)), but even these require pushing to a GitHub repo as standard.


This requires two things:

* A GitHub Account
* A working knowledge of how to interact with GitHub repositories.

Many of those coming from a more technical background may already have a working knowledge of how to interact with Git and GitHub via the command line (and will be familiar with processes such as e.g. `git commit`, `pull`, `push`, `clone`, etc.). If you are not, you may wish to explore the [introductory documentation](https://docs.github.com/en/get-started/start-your-journey/hello-world) in your own time. If you do not foresee yourself needing to invest more widely in knowing Git in the future, you may instead wish to work with [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) as a GUI-only alternative.

If you know either of these approaches, you are welcome to work with them today. If you do not, these instructions will be for working exclusively with GitHub repos through the online web GUI. This is not the most efficient way of interacting with Git, but will see us through the afternoon and the creation of your first personal website.

## A minimal Jekyll personal Website

!!! warning "Account Required"

    This tutorial requires a GitHub account. Hopefully you already created one before the session. If not, you can [do it now](https://github.com/signup).

A minimal personal website already exists on the `bristol-glaciology` GitHub organisation. The repo is [available here](https://github.com/bristol-glaciology/example-personal-website) and you can see how this appears once hosted [at the following link](https://bristol-glaciology.github.io/example-personal-website/). The website takes advantage of Jekyll using the Minimal Mistakes theme. It is a common theme that you might see replicated across many personal academic websites (including [Fabien's](https://fabienmaussion.info/) and [Tom's](https://trchudley.github.io/)).

## Constructing the Website

### Forking the Website

Rather than creating a website from scratch, we will start by creating our own copy of the example repository. On GitHub, this process is called **forking**.

Navigate to the example repository and click the **Fork** button in the top-right corner of the page. GitHub will then guide you through creating your own copy of the repository under your personal account.

!!! warning "Repository Name"

    For this tutorial, your repository **must** be named `<your-github-username>.github.io`.

    For example, if your GitHub username is `jane-smith`, your repository should be called `jane-smith.github.io`.

This naming convention is special. GitHub Pages automatically publishes repositories with this name at:

```text
https://<your-github-username>.github.io
```

When creating the fork, you can leave the default options selected. Once the fork has completed, you should find yourself in your own copy of the repository. Any changes you make from this point onwards will only affect your website.

### The website repo

The repository contains a number of files and folders, but only a few are important for getting started.

* `_pages/` contains the individual pages that make up the website.
* `assets/images/` contains images and other media used throughout the site.
* `_config.yml` contains the main website configuration.
* `README.md` provides an introduction to the repository and some useful links.
* `Gemfile` lists the software packages required to build the site locally.

You do not need to understand everything in the repository immediately. For this workshop, most of your time will be spent editing files within `_pages/`, uploading images to `assets/images/`, and updating information within `_config.yml`.

### Configuring the website (`_config.yml`)

The `_config.yml` file controls many aspects of how the website is built and displayed.

The file uses the YAML format. YAML stores information as simple key–value pairs:

```yaml
title: My Website
name: Jane Smith
email: jane.smith@university.ac.uk
```

You do not need to understand YAML in detail for this workshop. In most cases, you will simply replace the example values with your own information.

To edit a file within the GitHub web interface:

1. Navigate to the file within the repository.
2. Click on the file name to open it.
3. Select the pencil (**Edit this file**) button in the top-right corner.
4. Make your changes.
5. Select **Commit changes...** to save them.

When prompted, you can accept the default options and commit directly to the `main` branch.

Open `_config.yml` and update the fields describing the website owner, including your name, biography, affiliation, links, and other personal details. Many of these values are used automatically throughout the site, so it is worth spending a few minutes replacing the example information with your own.

The example configuration only includes a subset of the available options. If you wish to customise the website further, the Minimal Mistakes documentation contains [information about the full configuration file](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) and all available settings.

### Editing pages

Most website content is stored as Markdown files within the `_pages/` directory.

To edit a page, navigate to the relevant file and click the pencil (**Edit this file**) button. The file contents can then be modified directly within GitHub.

As a starting point, update the existing pages with your own information. For example, you may wish to:

* Replace the placeholder biography text.
* Add information about your research interests.
* Update links to personal profiles and external websites.
* Add your own images.

Once you have made a change, select **Commit changes...** to save it.

You may find it useful to keep a second browser tab open showing the website itself, allowing you to refresh the page and quickly check how your changes appear once they have been published.

### Adding pages

New pages can be added directly through the GitHub web interface.

Navigate to the `_pages/` directory and select **Add file** → **Create new file**. Give the file a suitable name ending in `.md`, for example:

```text
teaching.md
```

Each page begins with a block of YAML known as **front matter**. This defines information about the page and how it should be displayed.

A minimal page might look like:

```yaml
---
title: "Teaching"
permalink: /teaching/
layout: single
---

Content goes here.
```

The `layout` option controls the overall appearance of the page. Minimal Mistakes provides several layouts for different purposes, although for this workshop we will use the `single` layout throughout.

Further information on creating pages can be found in the Minimal Mistakes [pages documentation](https://mmistakes.github.io/minimal-mistakes/docs/pages/) and [layouts documentation](https://mmistakes.github.io/minimal-mistakes/docs/layouts/).

If you would like the page to appear in the site's navigation menu, you will also need to edit `_data/navigation.yml` and add a new navigation entry. The Minimal Mistakes documentation contains further information on [navigation configuration](https://mmistakes.github.io/minimal-mistakes/docs/navigation/).

### Adding images and other files

Images can be uploaded directly through the GitHub web interface.

Navigate to the `assets/images/` directory and select **Add file** → **Upload files**. You can then drag-and-drop images from your computer or browse for them manually.

Once uploaded, images can be included within pages using standard Markdown syntax:

```markdown
![Description of image](/assets/images/my-image.jpg)
```

As with any other change, remember to commit the uploaded files when prompted.

## Publishing the website

GitHub Pages must be enabled before the website becomes publicly accessible.

Open the repository **Settings** page and select **Pages** from the navigation menu. Under **Build and deployment**, choose **Deploy from a branch** if it is not already selected. The default branch (`main`) should normally be selected automatically.

You can find detailed instructions in the official [GitHub Pages documentation](https://docs.github.com/en/pages).

After saving the settings, GitHub will begin building the website. The first build may take a few minutes to complete.

You can monitor the progress of the build from the **Actions** tab of the repository. Once deployment has completed successfully, your website should be available at:

```text
https://<your-github-username>.github.io
```

Repositories named `<your-github-username>.github.io` are known as **user sites**. Each GitHub account can have one user site, and it is published directly at the root GitHub Pages address.

Additional websites can be created using other repository names. These are known as **project sites** and are published beneath the user site URL. For example, a repository called:

```text
research-project
```

would be published at:

```text
https://<your-github-username>.github.io/research-project/
```

For most academic personal websites, the user-site approach described in this tutorial is the simplest option. It provides a clean URL, requires no additional configuration, and is generally the approach used for personal academic websites.


## Advanced Topics

### Previewing the site locally

The workflow above edits files directly on GitHub and relies on GitHub Pages to build the site remotely. This is perfectly adequate for a simple personal website, but it can be slower when making many edits or experimenting with layouts.

If you are working locally on your computer, you can preview the site before pushing changes to GitHub.

#### Clone the repository

Clone your repository to your local machine:

```bash
git clone https://github.com/<your-github-username>/<your-github-username>.github.io.git
cd <your-github-username>.github.io
```

#### Install the site dependencies

This Jekyll site uses Ruby and Bundler. If Ruby is installed on your system, install the required dependencies with:

```bash
bundle install
```

You may need to install Bundler first:

```bash
gem install bundler
```

#### Start the local server

Run:

```bash
bundle exec jekyll serve
```

Jekyll will build the site and start a local web server, usually available at:

```text
http://localhost:4000
```

Open this address in your browser to preview the website. The server will automatically rebuild the site when you save changes to files.

#### Push changes to GitHub

Once you are happy with the result, commit and push your changes:

```bash
git add .
git commit -m "Update website"
git push
```

GitHub Pages will then rebuild and publish the updated site online.

!!! note

    Running the site locally requires additional software that is not needed for the GitHub web-GUI workflow described in this tutorial. If you only plan to make occasional edits to a personal website, working directly through GitHub is often the simpler option.

### Using your own domain

GitHub Pages sites are available by default at URLs such as:

```text
https://<your-github-username>.github.io
```

You can also use a custom domain, for example:

```text
https://www.example.com
```

Many academic researchers choose to purchase a personal domain name (e.g. Fabien's is at fabienmaussion.info, even though it is managed through a [standard GitHub repo](https://github.com/fmaussion/fmaussion.github.io)). This is useful if you expect to maintain a website over a long period of time. Doing so can make it easier to move between hosting providers in the future without changing the public address of the website. 

On the other hand, although Tom does own a personal domain name that redirects to his website (tom-chudley.com), he explicity chose to keep the github pages address (trchudley.github.io) as the address during his lectureship job hunt. Within Geography/Earth Sciences, where programming skills can vary, having a `.github.io` address can be a useful shibboleth for programming capability...


To set up a custom web domain, you will need to:

1. Purchase a domain name from a domain registrar.
2. Configure the domain's DNS records so that they point to GitHub Pages.
3. Add the domain name within the GitHub Pages settings for your repository.

[GitHub provides detailed instructions in the official documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

Once configured correctly, GitHub Pages will automatically serve your website from your custom domain and manage HTTPS certificates for you.

