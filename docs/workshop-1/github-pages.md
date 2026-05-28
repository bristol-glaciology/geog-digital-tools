# Hosting with GitHub Pages

!!! note "This page is a stub"
    Content will be added after the workshop. For now, see the links below.

[GitHub Pages](https://pages.github.com/) lets you host a static website directly from a GitHub repository, for free. Combined with a GitHub Actions workflow, your site can rebuild and redeploy automatically every time you push a commit.

## Why GitHub Pages

- **Free** for public repositories
- **Integrated** with your existing Git workflow
- **Reliable** — served by GitHub's CDN
- **Custom domains** supported (e.g. `yourname.github.io` or `yourdomain.com`)

## How it works with MkDocs / JupyterBook

You write content locally → push to GitHub → a GitHub Actions workflow builds your site → the output is deployed to the `gh-pages` branch → GitHub serves it.

```
your repo (main branch)
    └── docs/          ← your Markdown/notebooks
    └── mkdocs.yml     ← config
    └── .github/
        └── workflows/
            └── deploy.yml   ← build + deploy automatically
```

## Key links

- :material-book-open: [GitHub Pages documentation](https://docs.github.com/en/pages)
- :material-book-open: [Deploying MkDocs to GitHub Pages](https://squidfunk.github.io/mkdocs-material/publishing-your-site/)
- :material-book-open: [Deploying JupyterBook to GitHub Pages](https://jupyterbook.org/en/stable/publish/gh-pages.html)

## The one-command deploy (MkDocs)

```bash
mkdocs gh-deploy
```

That's it — MkDocs builds your site and pushes it to `gh-pages` in one step. The GitHub Actions approach is cleaner for ongoing projects, but this is perfect to get started.
