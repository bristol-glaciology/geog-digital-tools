# 5. Git and GitHub — the basics

Publishing a website with any of the tools in this workshop ultimately means putting your files somewhere on the internet. The standard way to do this — and the one all the tools here are built around — is [GitHub](https://github.com), which requires a basic understanding of **Git**.

## What is Git?

Git is a **version control system**: software that tracks changes to files over time. Every time you save a meaningful change, you create a *commit* — a snapshot of your project at that moment. This means you can see the full history of your work, revert to any previous state, and collaborate with others without overwriting each other's changes.

Git was designed for code, but it works equally well for any collection of text files — including Markdown websites.

## Git vs GitHub

**Git** is the tool; **GitHub** is a website that hosts Git repositories in the cloud and adds collaboration features on top. When you push your website files to a GitHub repository, GitHub can serve them publicly as a website via [GitHub Pages](https://docs.github.com/en/pages) — for free.

## Do I need to learn Git properly?

For the hands-on session, the answer is **no** — the [tutorial](hands-on.md) works entirely through the GitHub web interface. You click, type, and commit without ever opening a terminal.

That said, Git is probably the most transferable technical skill in this workshop. If you plan to use any of these tools regularly, investing a few hours in learning the basics will pay off quickly. A good starting point is [GitHub's own introduction](https://docs.github.com/en/get-started/start-your-journey/hello-world), or the [GitHub Desktop](https://docs.github.com/en/desktop/overview/getting-started-with-github-desktop) app if you prefer a graphical interface over the command line.

!!! note "This is the most technical part of the workshop"
    Git has a steeper learning curve than Markdown or `mkdocs serve`. If you get stuck during the hands-on session, ask — this is exactly where we expect people to need help.
