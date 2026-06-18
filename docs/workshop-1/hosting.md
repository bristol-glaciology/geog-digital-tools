# 4. Hosting

## Where do the files go?

Static site generators produce a folder of HTML, CSS, and JavaScript. You preview them locally with `mkdocs serve`, `jupyter book start`, or `bundle exec jekyll serve`. To share them, you need a **server**: a computer permanently connected to the internet.

You don't need to understand servers in depth to publish a website. Simply ask yourself: which server will host your files, and how do you get them there?

## Hosting options

### University or institutional servers

Some universities offer web hosting for staff and students, though this is increasingly rare — the University of Bristol, for instance, does not (as far as we are aware), and instead encourages users to operate exclusively within WordPress via the [Bristol Blogs service](https://www.bristol.ac.uk/research-it/our-remit/bristol-blogs-information/). If your institution does provide it, the limitations are the same regardless: you are dependent on your employer (your site disappears if you leave), customisation is typically restricted, and the update workflow is manual. Worth asking your IT department, but don't count on it.

### Commercial web hosting

Hosting is often bundled or available cheaply when you [buy a domain name](#side-quest-using-your-own-domain). You get an FTP or SFTP connection to upload your HTML files. This gives you a clean personal domain independent of any institution. The downside is a small annual cost and a manual upload workflow: every time you update your site, you need to re-upload the files.

### GitHub Pages

[GitHub Pages](https://docs.github.com/en/pages) is the option most people in this workshop will end up using, and the one we recommend for getting started. It hosts your site directly from a GitHub repository for free, with no server to manage. More importantly, it integrates naturally with the version control workflow that all the tools in this workshop are built around: you edit your content, commit the changes, push to GitHub, and the site updates automatically.

All of the tools covered in this workshop (MkDocs, JupyterBook, Jekyll) have first-class support for deploying with GitHub Pages. The [hands-on tutorial](hands-on.md) walks you through this.

!!! tip "Custom domains with GitHub Pages"

    GitHub Pages gives you `yourusername.github.io`. Point your own domain (bought from OVH, Namecheap, etc.) at it for the best of both: clean GitHub Pages deployment plus a permanent personal URL that survives moving institutions.

### ReadTheDocs

[ReadTheDocs](https://about.readthedocs.com) is a hosting platform built specifically for software documentation. It connects to your GitHub repository, builds your Sphinx or MkDocs site automatically when you push, and hosts it at a `yourproject.readthedocs.io` URL. It supports versioned documentation (useful if your software has multiple releases) and is widely used in the Python ecosystem. It is the natural choice if you are documenting a Python package — for everything else, GitHub Pages is simpler.

If you would like to explore ReadTheDocs, you can (see instructions for [MkDocs](https://docs.readthedocs.com/platform/stable/intro/mkdocs.html) and [MyST/Jupyter Book](https://mystmd.org/guide/deployment-readthedocs)) on their respective websites.


## Side quest: using your own domain

GitHub Pages assigns URLs like:

```text
https://<your-github-username>.github.io
```

You can also buy a custom domain, so your domain will be e.g.:

```text
https://www.my-name.com
```

Many academic researchers choose to purchase a personal domain name (e.g. Fabien's is at fabienmaussion.info, even though it is managed through a [standard GitHub repo](https://github.com/fmaussion/fmaussion.github.io)). This is useful if you expect to maintain a website over a long period of time. Doing so can make it easier to move between hosting providers in the future without changing the public address of the website. 

On the other hand, although Tom does own a personal domain name that redirects to his website (tom-chudley.com), he explicity chose to keep the github pages address (trchudley.github.io) as the address during his lectureship job hunt. Within Geography/Earth Sciences, where programming skills can vary, having a `.github.io` address can be a useful shibboleth for programming capability...

To set up a custom domain:

1. Purchase a domain name from a domain registrar (e.g. from [OVH](https://www.ovhcloud.com), [Namecheap](https://www.namecheap.com), or similar).
2. Configure the domain's DNS records so that they point to GitHub Pages.
3. Add the domain name within the GitHub Pages settings for your repository.

[GitHub provides detailed instructions in the official documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

Once configured correctly, GitHub Pages will automatically serve your website from your custom domain and manage HTTPS certificates for you.
