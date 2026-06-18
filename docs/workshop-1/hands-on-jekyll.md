# A minimal workflow to create a Jekyll site hosted by Github pages

!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and Jekyll/Minimal Mistakes, but full documentation is also available online:

    - [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
    - [GitHub Pages](https://docs.github.com/en/pages)

This page shows how to quickly create a Jekyll website based on the [Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide). It is a common theme that you might see replicated across many personal academic websites (including [Fabien's](https://fabienmaussion.info/) and [Tom's](https://trchudley.github.io/)).

We will create this by replicating a minimal personal website that already exists on the `bristol-glaciology` GitHub organisation. The repo is [available here](https://github.com/bristol-glaciology/example-jekyll-website) and you can see how this appears once hosted [at the following link](https://bristol-glaciology.github.io/example-jekyll-website/).

## Two ways to build your site

Pick whichever suits you. **Neither requires git experience or command line.** 

|                       | In your browser *(recommended for beginners)* | On your own computer                  |
| --------------------- | -------- | ----- |
| **GitHub account?**   | Yes (free, 2 minutes)                       | Not needed                                            |
| **Install anything?** | No                                  | Yes (Ruby + Bundler)                                  |
| **Command line?**     | Never                                               | A little                                              |
| **Best if…**          | New to this, want a site online today | Don't want an account, or prefer offline work |

The main tutorial uses the **browser route**: no software, no command line—just click and type on GitHub. To work offline without an account, skip to [Build locally](#alternative-build-locally-no-github-account-needed).

## Setting up: your GitHub account

GitHub stores your project and publishes it via [GitHub Pages](https://docs.github.com/en/pages) for free. For the browser route, create a free account.

!!! tip "You don't need to learn Git to follow this tutorial"

    Everything below is done by clicking and typing in your browser.

!!! warning "You'll need a free GitHub account"

    [Create one now](https://github.com/signup) in two minutes. Don't want one? Use the [build-locally route](#alternative-build-locally-no-github-account-needed).

!!! note "Already comfortable with Git?"

    Use the command line or [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) if you prefer. For fundamentals, see [GitHub's Hello World intro](https://docs.github.com/en/get-started/start-your-journey/hello-world).

## Forking the website from GitHub

Create your own copy of the example repository (called **forking**), instead of creating a website from scratch:

1. Go to the [example repository](https://github.com/bristol-glaciology/example-jekyll-website).
2. Click **Fork** (top-right).
3. GitHub guides you through creating your own copy in your own account.

!!! warning "Repository Name"

    For this tutorial, your repository **must** be named `<your-github-username>.github.io`.

    For example, if your GitHub username is `alice`, your repository should be called `alice.github.io`.

This naming convention is special. GitHub Pages automatically publishes repositories with this name at:

```text
https://<your-github-username>.github.io
```

When creating the fork, you can leave the default options selected. Once the fork has completed, you should find yourself in your own copy of the repository. Any changes you make from this point onwards will only affect your website.

![Fork interface](img/fork.png)

**Remember to replace the text with** `https://<your-github-username>.github.io`

## Constructing the Website

### The website repo

The repository contains a number of files and folders, but only a few are important for getting started.

* `_pages/` contains the individual pages that make up the website.
* `assets/images/` contains images and other media used throughout the site.
* `_config.yml` contains the main website configuration.
* `README.md` provides an introduction to the repository and some useful links.
* `Gemfile` lists the software packages required to build the site locally.

You do not need to understand everything in the repository immediately. For this workshop, most of your time will be spent editing `_pages/`, uploading images to `assets/images/`, and updating `_config.yml`.

### Configuring the website (`_config.yml`)

`_config.yml` controls how the website builds and displays. It uses YAML format which stores simple key-value pairs:

```yaml
title: My Website
name: Jane Smith
email: jane.smith@university.ac.uk
```

You do not need to understand YAML in detail for this workshop. In most cases, you will simply replace the example values with your own information.
To edit a file with GitHub's web interface:
1. Click on the file name.
2. Click the pencil (**Edit this file**) button top-right corner.
3. Make your changes.
4. Click **Commit changes...** to save them.
5. Accept the default options and commit directly to the `main` branch.

Open `_config.yml`. Update your name, biography, affiliation, and links. Most values appear automatically throughout the site, so it is worth replacing the example information with your own.

The example configuration only includes a subset of the available options. See [Minimal Mistakes docs](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) for all options.

### Editing pages

Most content is stored in Markdown files in `_pages/`.

To edit a page, navigate to the relevant file and click the pencil (**Edit this file**) button. The file contents can then be modified directly within GitHub.

Update the existing pages with your own information. You may wish to:

* Replace the placeholder biography text.
* Add information about your research interests.
* Update links to personal profiles and external websites.
* Add your own images.

Once you have made a change, select **Commit changes...** to save it.

You can keep a second browser tab open showing the website itself. You can refresh the page and quickly check how your changes appear.

### Adding pages

Create a new page:
1. Go to `_pages/`.
2. Click **Add file** → **Create new file**.
3. Name it e.g. `teaching.md`.

Each page begins with a block of YAML known as **front matter**. This defines information about the page and how it should be displayed:

```yaml
---
title: "Teaching"
permalink: /teaching/
layout: single
---

Content goes here.
```

The `layout` option controls appearance. For this workshop, use the `single` layout.

To add a page to the navigation menu, edit `_data/navigation.yml` and add an entry. See [Minimal Mistakes pages docs](https://mmistakes.github.io/minimal-mistakes/docs/pages/) and [layouts docs](https://mmistakes.github.io/minimal-mistakes/docs/layouts/) for more information.

### Adding images and other files

Upload images through the GitHub web interface:
1. Go to `assets/images/`.
2. Click **Add file** → **Upload files**.
3. Drag-and-drop or browse files.

Include uploaded images in pages using Markdown:

```markdown
![Description of image](/assets/images/my-image.jpg)
```

Remember to commit uploaded files when prompted.

## Publishing the website on GitHub Pages

Enable GitHub Pages to make the website publicly accessible:
1. Go to repository **Settings**.
2. Select **Pages** from the menu.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Select `main` branch.

You can find detailed instructions in the official [GitHub Pages documentation](https://docs.github.com/en/pages).
GitHub saves your settings and builds the site. Check progress in the **Actions** tab as the first time make take a few minutes to complete.

Once complete, your website will be available at:
```text
https://<your-github-username>.github.io
```

Repositories named `<username>.github.io` are **user sites**, published at the root GitHub Pages address. Each account can have one user site. Other repositories are **project sites**, published under the user site's URL.
For example, a repository called:

```text
research-project
```

would be published at:

```text
https://<your-github-username>.github.io/research-project/
```

For most academic personal websites, the user-site approach is simplest. It provides a clean URL, requires minimal setup, and is standard for personal academic sites.


## Alternative: build locally (no GitHub account needed)

The workflow above edits files on GitHub through the web interface, which is the easiest way, but requires a free account. If you'd rather not have an account, download the template and build locally. You only need an account to publish online.

!!! warning "You'll need to use the command line"

    In Windows this will be Powershell, in MacOS or Linux this will be your Terminal.

This local route also has advantages even if you do have an account: it is faster when making many edits or experimenting with layouts, since you can preview changes instantly before pushing them.

### Get the template

- **No account:** click **Code** → **Download ZIP** on the [example repository](https://github.com/bristol-glaciology/example-jekyll-website), then unzip on your computer.
- **With an account:** clone your fork instead, so you can push changes back and publish later:

    ```bash
    git clone https://github.com/<your-github-username>/<your-github-username>.github.io.git
    cd <your-github-username>.github.io
    ```

### Install Ruby and Jekyll

Building the site on your own computer needs **Ruby** (the language Jekyll is written in) plus a couple of small build tools. There are two ways to get them — pick whichever suits you.

=== "With micromamba / conda"

    If you already use micromamba or conda — for example for the MkDocs or JupyterBook paths — this keeps everything in one place and works the same on every platform. Create an environment with Ruby and a compiler, then activate it:

    ```bash
    micromamba create -n jekyll -c conda-forge ruby cxx-compiler make
    micromamba activate jekyll
    ```

    Then install Jekyll and Bundler into it:

    ```bash
    gem install bundler jekyll
    ```

    Remember to run `micromamba activate jekyll` each time you open a new terminal to work on your site.

    !!! note "Tested on macOS so far"

        We've tested this route on macOS, where it works nicely. It should behave the same on Windows and Linux, but we haven't confirmed that yet. If anything misbehaves on the day, just switch to the native Ruby tab — or fall back to the no-install [browser route](#two-ways-to-build-your-site). Either way, let us know!

=== "With a native Ruby install"

    The conventional route is to follow the official Jekyll documentation:

    - [**macOS**](https://jekyllrb.com/docs/installation/macos/)
    - [**Windows**](https://jekyllrb.com/docs/installation/windows/)
    - [**Linux**](https://jekyllrb.com/docs/installation/ubuntu/)

    Then install Jekyll and Bundler:

    ```bash
    gem install jekyll bundler
    ```

Now, from inside the website folder, install the site's own dependencies (the extra gems listed in its `Gemfile`):

```bash
bundle install
```

### Start the local server

Run:

```bash
bundle exec jekyll serve --livereload
```

Jekyll will build the site and start a local web server, usually available at:

```text
http://localhost:4000
```

Open this address in your browser to preview the website. The server will automatically rebuild the site when you save changes to files.

### Push changes to GitHub

Once you are happy with the result, commit and push your changes:

```bash
git add .
git commit -m "Update website"
git push
```

GitHub Pages will then rebuild and publish the updated site online.

!!! note

    Running the site locally requires additional software that is not needed for the GitHub web-GUI workflow described in this tutorial. If you only plan to make occasional edits to a personal website, working directly through GitHub is often the simpler option.

