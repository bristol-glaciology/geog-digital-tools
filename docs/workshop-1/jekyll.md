# 3.3 Jekyll (Minimal Mistakes)

[Jekyll](https://jekyllrb.com/) converts Markdown files into static websites using templates and configuration. Paired with [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme, it provides a pre-built structure for personal sites, portfolios, and blogs. This comes with sensible defaults for navigation, posts, and layouts. For our purposes, it is likely the most popular and robust Jekyll theme available.

Jekyll runs on many personal academic sites. See the [tool comparison table](intro-static-sites.md#the-tools-we-cover-today) for when to use Jekyll versus MkDocs or JupyterBook.

!!! note "Jekyll and GitHub Pages"

    GitHub Pages natively supports Jekyll, so sites build and deploy automatically from your repository with no separate pipeline (e.g. GitHub Actions).

## Getting Started with Jekyll and Minimal Mistakes

!!! tip "Workshop shortcut"

    For the hands-on session, **fork a ready-made template** instead - much faster! See the [hands-on tutorial](hands-on-jekyll.md) when you are ready to build your website.

    The steps below are for those who want to understand how Jekyll works from the ground up, or who need to set up a project independently.

The [official Jekyll](https://jekyllrb.com/docs/) and [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) documentation are comprehensive. A typical from-scratch workflow can be found on the [Minimal Mistakes Documentation](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) and is broadly as follows:

### 1. Install prerequisites: Ruby and Bundler

Jekyll requires Ruby and the Bundler package manager.

On most systems:

~~~bash
# check Ruby is installed
ruby -v

# install bundler
gem install bundler
~~~

On macOS, Ruby is often installed via Homebrew or system tools; on Linux, use your package manager. On Windows, you can work within the Windows Subsystem for Linux, or use [RubyInstaller](https://rubyinstaller.org/).

### 2. Install Jekyll

~~~bash
gem install jekyll
~~~

Verify installation:

~~~bash
jekyll -v
~~~

### 3. Create a new site

~~~bash
jekyll new my-site --skip-bundle
cd my-site
~~~

This creates a basic scaffold including:

- `_config.yml` (global configuration)
- `_posts/` (blog posts)
- `index.md` (homepage)

### 4. Add Bundler dependencies

~~~bash
bundle init
~~~

Then edit the `Gemfile` to include Jekyll and Minimal Mistakes:

~~~ruby
gem "jekyll", "~> 4.3"
gem "minimal-mistakes-jekyll"
~~~

Install dependencies:

~~~bash
bundle install
~~~

### 5. Configure Minimal Mistakes

Edit `_config.yml` to enable the theme. There are two ways to do this:

**Gem-based** (requires local Ruby setup, as above):

~~~yaml
theme: minimal-mistakes-jekyll
~~~

**Remote theme** (simpler — no local Ruby install needed, works directly on GitHub Pages):

~~~yaml
remote_theme: mmistakes/minimal-mistakes
~~~

The remote theme approach is often the more practical choice if you only plan to edit your site through GitHub's web interface. Either way, also set your site's basic metadata:

~~~yaml
title: My Personal Site
description: A short site description
url: "https://yourusername.github.io"
minimal_mistakes_skin: "default"
~~~

A [full introduction to the `_config.yml` file can be found here](https://mmistakes.github.io/minimal-mistakes/docs/configuration/).

Minimal Mistakes supports extensive configuration for navigation, author profiles, and layouts.

A typical navigation structure (i.e. the structure of links in the header bar) is defined in `_data/navigation.yml`:

~~~yaml
main:
  - title: "About"
    url: /about/
  - title: "Posts"
    url: /posts/
  - title: "Projects"
    url: /projects/
~~~

[More info on the navbar here](https://mmistakes.github.io/minimal-mistakes/docs/navigation/).

### 6. Add content

Content is written in Markdown with YAML front matter.

Example page:

~~~markdown
---
title: About
layout: single
permalink: /about/
---

This is a personal website built with Jekyll and Minimal Mistakes.
~~~

More information about [pages](https://mmistakes.github.io/minimal-mistakes/docs/pages/) and [layouts](https://mmistakes.github.io/minimal-mistakes/docs/layouts/) can be found in the documentation.

If you would like an active blog or news page, this is also possible using [Posts](https://mmistakes.github.io/minimal-mistakes/docs/posts/). Blog posts go in `_posts/` with the naming format `YYYY-MM-DD-title.md`.

### 7. Build and preview locally

~~~bash
bundle exec jekyll serve
~~~

The site will be available at `http://localhost:4000`. The server rebuilds automatically when files change.

### 8. Deploy to GitHub Pages

Jekyll is natively supported by GitHub Pages. After you push to a repo, simply enable **Pages** in repository settings and set **Deploy from a branch** → **main**. No GitHub Actions workflow required.
