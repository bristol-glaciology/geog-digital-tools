# 3. Setup: Python & tools

MkDocs and JupyterBook are Python tools — you need Python installed on your computer before following sections 3.1 and 3.2. This page walks you through two options and then shows you how to install the tools themselves.

!!! warning "Jekyll users: skip this page"
    If you're following the [Jekyll route](jekyll.md), you don't need Python. The [hands-on tutorial](hands-on.md) works entirely through the GitHub web interface with no local software needed.

!!! note "First time? No rush"
    The instructions below can look daunting. Skip this and come to the workshop day. We'll help everyone get set up on the day.

!!! tip "Already have Python?"
    If you have Anaconda, Miniconda, Conda, or similar working on your machine, skip to [Installing the tools](#installing-the-tools).

## Installing Python

### Option 1 — Micromamba (recommended)

[Micromamba](https://mamba.readthedocs.io/en/latest/user_guide/micromamba.html) is a tiny, standalone package manager. Unlike Anaconda, it ships as a single small binary: no pre-installed packages, no 3GB base environment. It's fast, takes minimal space, and is what we use with students.

=== "Windows"

    Open **PowerShell** (search for it in the Start menu) and paste the following command:

    ```powershell
    Invoke-Expression ((Invoke-WebRequest -Uri https://micro.mamba.pm/install.ps1 -UseBasicParsing).Content)
    ```

    Follow the prompts. When asked about shell initialisation, answer **yes**. Once finished, **close and reopen PowerShell**.

    !!! warning "Installation path"
        When asked where to install, choose a folder with no spaces or special characters in its name, for example `C:\Users\yourname\micromamba`.

=== "macOS & Linux"

    Open a **Terminal** and paste:

    ```bash
    "${SHELL}" <(curl -L micro.mamba.pm/install.sh)
    ```

    Follow the prompts. When asked about shell initialisation, answer **yes**. Once finished, **close and reopen the terminal**.

**Verify the installation** by opening a new terminal and typing:

```bash
micromamba --version
```

You should see a version number (e.g., `2.1.0`). If you see "command not found", close and reopen the terminal and try again.

---

### Option 2 — Anaconda

[Anaconda](https://www.anaconda.com/download) is a large, all-in-one Python distribution with hundreds of pre-installed packages and a graphical interface. It installs ~3GB of software, much more than needed for MkDocs or JupyterBook, but works perfectly and may feel more approachable if you prefer a GUI installer.

Download and run the installer from [anaconda.com/download](https://www.anaconda.com/download).

!!! warning "Windows users"
    On Windows, use the **Anaconda Prompt** (installed to the Start menu) for all commands below — not PowerShell or the regular Command Prompt.

---

## Installing the tools

Once Python is set up, install whichever tool you plan to use. If you're unsure, install both—they coexist without issue.

### MkDocs Material

=== "micromamba"

    ```bash
    micromamba create -n webdev -c conda-forge mkdocs-material -y
    micromamba activate webdev
    ```

    The first command creates a new environment called `webdev` and installs MkDocs Material into it. The second activates it — **you will need to run `micromamba activate webdev` each time you open a new terminal**.

=== "Anaconda / conda"

    ```bash
    conda install -c conda-forge mkdocs-material
    ```

Verify with:

```bash
mkdocs --version
```

You should see something like `mkdocs, version 1.6.x`.

### JupyterBook

=== "micromamba"

    If you already created the `webdev` environment above, add JupyterBook to it:

    ```bash
    micromamba activate webdev
    micromamba install -c conda-forge jupyter-book
    ```

    Otherwise, create a new environment:

    ```bash
    micromamba create -n webdev -c conda-forge jupyter-book -y
    micromamba activate webdev
    ```

=== "Anaconda / conda"

    ```bash
    conda install -c conda-forge jupyter-book
    ```

Verify with:

```bash
jupyter-book --version
```

!!! note "Using pip instead"
    If you have a Python installation that does not use conda (e.g. a system Python or a virtual environment), pip works too:

    ```bash
    pip install mkdocs-material
    pip install jupyter-book
    ```
