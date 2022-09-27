---
id: noikg9qekz2t74b0mmfwh39
title: Poetry
desc: ''
updated: 1652632313891
created: 1652606285505
---
# [Poetry](https://python-poetry.org/)

ref: [jayway](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/)

`Poetry` is a packaging and dependency manager. It resolves your library dependencies. Besides virtual environment and dependency management, `poetry` could be used to create a boilerplate for your new project, build a project, etc.

The main file of your poetry project is the `pyproject.toml` file.
- you use it to specify the requirements (your package), the dev-requirements (development dependencies) and project metadata
- `poetry` uses the `.toml` file to resolve the dependencies of your defined requirements
- when you install dependencies, poetry creates the `poetry.lock` file where it stores the exact versions of the dependencies after it has resolved them
- `poetry` then creates a virtual environment and installs everything from the `.lock` file. You should add this file under the version control so that your collaborators later can replicate your virtual environment.

Some alternatives to poetry for virtual environments are [[virtualenv|notes.tutorial.python.virtual-environment.virtualenv]], `conda`, [[venv|notes.tutorial.python.virtual-environment.venv]] or `pipenv`.

## Setup Jupyter in Poetry

![[notes.tutorial.python.virtual-environment.poetry.jupyter-in-poetry#setup-jupyter-in-poetry,1]]