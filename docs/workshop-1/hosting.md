# 4. Hosting

## Where do the files go?

A static site generator produces a folder of HTML, CSS, and JavaScript files. On your laptop, you can preview them with `mkdocs serve` (MkDocs) or `jupyter book start` (Jupyter Book) or `bundle exec jekyll serve` (Jekyll) — but for anyone else to see your site, those files need to live on a **server**: a computer that is permanently connected to the internet and responds to requests from web browsers.

You don't need to understand servers in depth to publish a website. The question is simply: which server will host your files, and how do you get them there?

## Hosting options

### University or institutional servers

Some universities offer web hosting for staff and students, though this is increasingly rare — the University of Bristol, for instance, does not (as far as we are aware), and instead encourages users to operate exclusively within WordPress via the [Bristol Blogs service](https://www.bristol.ac.uk/research-it/our-remit/bristol-blogs-information/). If your institution does provide it, the limitations are the same regardless: you are dependent on your employer (your site disappears if you leave), customisation is typically restricted, and the update workflow is manual. Worth asking your IT department, but don't count on it.

### Commercial web hosting

When you [purchase a domain name](#side-quest-using-your-own-domain), hosting is often bundled or available cheaply. You get an FTP or SFTP connection to upload your HTML files. This works, gives you a clean personal domain, and is independent of any institution. The downside is a small annual cost and a manual upload workflow — every time you update your site, you need to re-upload the files.

### GitHub Pages

[GitHub Pages](https://docs.github.com/en/pages) is the option most people in this workshop will end up using, and the one we recommend for getting started. It hosts your site directly from a GitHub repository — for free, with no server to manage. More importantly, it integrates naturally with the version control workflow that all the tools in this workshop are built around: you edit your content, commit the changes, push to GitHub, and the site updates automatically.

All of the tools covered in this workshop (MkDocs, JupyterBook, Jekyll) have first-class support for GitHub Pages deployment. The [hands-on tutorial](hands-on.md) walks through this in practice.

!!! tip "Custom domains with GitHub Pages"

    GitHub Pages gives you a URL like `yourusername.github.io`. You can point your own domain (bought from OVH, Namecheap, etc.) at it, getting the best of both worlds: the clean deployment workflow of GitHub Pages and a permanent personal URL that survives moving institutions.

### ReadTheDocs

[ReadTheDocs](https://about.readthedocs.com) is a hosting platform built specifically for software documentation. It connects to your GitHub repository, builds your Sphinx or MkDocs site automatically when you push, and hosts it at a `yourproject.readthedocs.io` URL. It supports versioned documentation (useful if your software has multiple releases) and is widely used in the Python ecosystem. It is the natural choice if you are documenting a Python package — for everything else, GitHub Pages is simpler.

If you would like to explore ReadTheDocs, you can (see instructions for [MkDocs](https://docs.readthedocs.com/platform/stable/intro/mkdocs.html) and [MyST/Jupyter Book](https://mystmd.org/guide/deployment-readthedocs)) on their respective websites.


## Side quest: using your own domain

GitHub Pages sites are available by default at URLs such as:

```text
https://<your-github-username>.github.io
```

You can also purchase a custom domain, so your domain will be e.g.:

```text
https://www.my-name.com
```

Many academic researchers choose to purchase a personal domain name (e.g. Fabien's is at fabienmaussion.info, even though it is managed through a [standard GitHub repo](https://github.com/fmaussion/fmaussion.github.io)). This is useful if you expect to maintain a website over a long period of time. Doing so can make it easier to move between hosting providers in the future without changing the public address of the website. 

On the other hand, although Tom does own a personal domain name that redirects to his website (tom-chudley.com), he explicity chose to keep the github pages address (trchudley.github.io) as the address during his lectureship job hunt. Within Geography/Earth Sciences, where programming skills can vary, having a `.github.io` address can be a useful shibboleth for programming capability...

To set up a custom web domain, you will need to:

1. Purchase a domain name from a domain registrar (e.g. from [OVH](https://www.ovhcloud.com), [Namecheap](https://www.namecheap.com), or similar).
2. Configure the domain's DNS records so that they point to GitHub Pages.
3. Add the domain name within the GitHub Pages settings for your repository.

[GitHub provides detailed instructions in the official documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

Once configured correctly, GitHub Pages will automatically serve your website from your custom domain and manage HTTPS certificates for you.
