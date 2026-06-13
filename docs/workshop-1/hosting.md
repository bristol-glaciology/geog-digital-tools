# 4. Hosting

## Where do the files go?

A static site generator produces a folder of HTML, CSS, and JavaScript files. On your laptop, you can preview them with `mkdocs serve` or `jupyter book start` — but for anyone else to see your site, those files need to live on a **server**: a computer that is permanently connected to the internet and responds to requests from web browsers.

You don't need to understand servers in depth to publish a website. The question is simply: which server will host your files, and how do you get them there?

## Hosting options

### University or institutional servers

Some universities offer web hosting for staff and students, though this is increasingly rare — the University of Bristol, for instance, does not (as far as we are aware). If your institution does provide it, the limitations are the same regardless: you are dependent on your employer (your site disappears if you leave), customisation is typically restricted, and the update workflow is manual. Worth asking your IT department, but don't count on it.

### Commercial web hosting

When you purchase a domain name (e.g. from [OVH](https://www.ovhcloud.com), [Namecheap](https://www.namecheap.com), or similar), hosting is often bundled or available cheaply. You get an FTP or SFTP connection to upload your HTML files. This works, gives you a clean personal domain, and is independent of any institution. The downside is a small annual cost and a manual upload workflow — every time you update your site, you need to re-upload the files.

### GitHub Pages

[GitHub Pages](https://docs.github.com/en/pages) is the option most people in this workshop will end up using, and the one we recommend for getting started. It hosts your site directly from a GitHub repository — for free, with no server to manage. More importantly, it integrates naturally with the version control workflow that all the tools in this workshop are built around: you edit your content, commit the changes, push to GitHub, and the site updates automatically.

All of the tools covered in this workshop (MkDocs, JupyterBook, Jekyll) have first-class support for GitHub Pages deployment. The [hands-on tutorial](hands-on.md) walks through this in practice.

!!! tip "Custom domains with GitHub Pages"

    GitHub Pages gives you a URL like `yourusername.github.io`. You can point your own domain (bought from OVH, Namecheap, etc.) at it, getting the best of both worlds: the clean deployment workflow of GitHub Pages and a permanent personal URL that survives moving institutions.

### ReadTheDocs

[ReadTheDocs](https://about.readthedocs.com) is a hosting platform built specifically for software documentation. It connects to your GitHub repository, builds your Sphinx or MkDocs site automatically when you push, and hosts it at a `yourproject.readthedocs.io` URL. It supports versioned documentation (useful if your software has multiple releases) and is widely used in the Python ecosystem. It is the natural choice if you are documenting a Python package — for everything else, GitHub Pages is simpler.

## Side quest: web analytics

Once your site is live, you may want to know how many people visit it and which pages they read. All the tools in this workshop support analytics — MkDocs Material has [built-in configuration](https://squidfunk.github.io/mkdocs-material/setup/setting-up-site-analytics/) for it, and Jekyll's Minimal Mistakes theme does too; for JupyterBook you add a small script snippet to the HTML header.

The default choice is often **Google Analytics**, which is free and widely supported. There are two reasons to think twice before using it. The first is practical: GA drops tracking cookies in visitors' browsers, which technically requires a cookie consent banner under GDPR — an annoying addition to an otherwise clean academic site. The second is ethical: by embedding GA, you are sending detailed behavioural data about your readers to Google, who uses it for their own purposes (ad targeting, profiling). For some academics, there is something uncomfortable about routing their audience's reading habits through a surveillance advertising platform — even if it is technically legal.

A cleaner alternative is **[Plausible](https://plausible.io)**: cookieless, privacy-respecting, and no consent banner needed. The cloud-hosted version costs around €9/month, which is fine for a funded project but not for a personal site. The self-hosted version is free and open-source — [OGGM](https://oggm.org) runs its own Plausible server, which anyone in the project can use at no cost, though someone has to maintain the server. [GoatCounter](https://www.goatcounter.com) is another cookieless option with a generous free tier.

For a personal academic website with modest traffic, any of these works. For a project site where you care about GDPR compliance, Plausible is worth the effort.
