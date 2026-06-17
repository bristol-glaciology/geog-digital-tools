# A minimal workflow to create a Jekyll site hosted by Github pages

!!! note "External Documentation"

    This page aims to provide a streamlined tutorial for GitHub Pages and Jekyll/Minimal Mistakes, but full documentation is also available online:

    - [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
    - [GitHub Pages](https://docs.github.com/en/pages)

This page shows how to quickly create a Jekyll website based on the [Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide). It is a common theme that you might see replicated across many personal academic websites (including [Fabien's](https://fabienmaussion.info/) and [Tom's](https://trchudley.github.io/)).

We will create this by replicating a minimal personal website that already exists on the `bristol-glaciology` GitHub organisation. The repo is [available here](https://github.com/bristol-glaciology/example-jekyll-website) and you can see how this appears once hosted [at the following link](https://bristol-glaciology.github.io/example-jekyll-website/).

## Two ways to build your site

There are two ways to follow this tutorial. **Neither requires any prior experience with Git or the command line.** Pick whichever suits you:

|                       | In your browser *(recommended for beginners)*       | On your own computer                                  |
| --------------------- | --------------------------------------------------- | ----------------------------------------------------- |
| **GitHub account?**   | Yes — free, takes two minutes                       | Not needed                                            |
| **Install anything?** | No                                                  | Yes — Ruby + Bundler                                  |
| **Command line?**     | Never                                               | A little                                              |
| **Best if…**          | you're new to all this and want a site online today | you'd rather not create an account, or want to work offline |

The main tutorial below uses the **browser route**: no software to install and no command line — you just click and type on the GitHub website. If you would prefer to work offline without an account, skip ahead to [Build locally](#alternative-build-locally-no-github-account-needed).

## Setting up: your GitHub account

GitHub is a free website that stores your project and can publish it online for you, through a feature called [GitHub Pages](https://docs.github.com/en/pages). For the browser route, a free account is the only setup you need.

!!! tip "You do not need to learn \"Git\" to follow this tutorial"

    You may have heard that GitHub involves a command line and cryptic commands like `commit`, `push` and `clone`. **You can ignore all of that here.** Everything below is done by clicking buttons and typing in your browser.

!!! warning "You'll need a free GitHub account"

    If you don't have one yet, [create one now](https://github.com/signup) — it only takes a couple of minutes. Don't want an account at all? Use the [build-locally route](#alternative-build-locally-no-github-account-needed) instead.

!!! note "Already comfortable with Git?"

    If you already know your way around Git and GitHub, you are welcome to use the command line or [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) today instead of the web interface. To learn the fundamentals properly in your own time, GitHub's [Hello World introduction](https://docs.github.com/en/get-started/start-your-journey/hello-world) is a good starting point.

## Forking the website from GitHub

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


## Constructing the Website


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

## Publishing the website on GitHub Pages

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


## Alternative: build locally (no GitHub account needed)

The workflow above edits files directly on GitHub through the web interface — the easiest route, but it requires a (free) GitHub account. If you would rather **not** create an account, you can instead download the template and build the site on your own computer. You only ever need an account if and when you decide to publish online.

This local route also has advantages even if you do have an account: it is faster when making many edits or experimenting with layouts, since you can preview changes instantly before pushing them.

### Get the template

- **No account:** on the [example repository](https://github.com/bristol-glaciology/example-jekyll-website), click the green **Code** button → **Download ZIP**, then unzip it on your computer.
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

    The conventional route is to install Ruby directly:

    - **macOS:** the cleanest option is [Homebrew](https://brew.sh): `brew install ruby`. (The Ruby that ships with macOS is old and awkward for installing gems, so a Homebrew Ruby is recommended.)
    - **Windows:** download and run [RubyInstaller](https://rubyinstaller.org/), choosing the version **with the DevKit** — this includes the build tools Jekyll needs.
    - **Linux:** install Ruby and its development headers via your package manager, e.g. `sudo apt install ruby-full build-essential` on Debian/Ubuntu.

    Then install Jekyll and Bundler:

    ```bash
    gem install bundler jekyll
    ```

Now, from inside the website folder, install the site's own dependencies (the extra gems listed in its `Gemfile`):

```bash
bundle install
```

### Start the local server

Run:

```bash
bundle exec jekyll serve
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

