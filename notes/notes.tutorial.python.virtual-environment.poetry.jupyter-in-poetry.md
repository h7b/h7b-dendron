---
id: 3k0n1c6p4b81ugvg085nza4
title: Jupyter in Poetry
desc: ''
updated: 1652751576146
created: 1652632280394
---
# Setup Jupyter in Poetry

ref: [MungingData | Amazing Python Data Workflow with Poetry, Pandas, and Jupyter](https://mungingdata.com/python/jupyter-workflow-poetry-pandas/)

[[Poetry|notes.tutorial.python.virtual-environment.poetry]] makes it easy to install Pandas and Jupyter to perform data analyses.

The workflow outlined here makes projects that can easily be run on other machines. Your teammates can easily run `poetry install` to setup an identical Jupyter development environment on their computers.

## Install

### Install `pandas`, `numpy`, `jupyter` with `poetry`

- Install `poetry` following its [documentation](https://python-poetry.org/docs/#installation)
- Create a new project called `blake`
    ```shell
    poetry new blake
    ```
- Change into the `blake` directory with `cd blake`.
- Install the dependencies that are required for running notebooks on your local machine 
    - This command downloads a bunch of Python code in the `~/Library/Caches/pypoetry/virtualenvs/blake-Y_2IcspR-py3.7/ directory`. This is referred to as the “virtual environment” of your project
    ```shell
    poetry add numpy pandas jupyter ipykernel
    ```
    - By default, poetry uses a separate cache directory `{cache-dir}/virtualenvs`, where it stores all virtual environment related files. ^gaqhf9yjjqhs
        - You can change the `cache-dir` value by editing the poetry config
        - Additionally, you can use the `virtualenvs.in-project` configuration variable to create virtual environment within your project directory
        - Specifically, running the command in Terminal tells poetry to create virtual environment directory (`.venv`) inside a project directory
        ```python
        poetry config virtualenvs.in-project true
        ``` 
- Now, `pyproject.toml` should look similar as follows
    ```toml
    [tool.poetry]
    name = "poetry"
    version = "0.1.0"
    description = ""
    authors = [""]
    
    [tool.poetry.dependencies]
    python = "^3.8"
    numpy = "^1.21.1"
    pandas = "^1.1.1"
    jupyter = "^1.0.0"
    ipykernel = "^5.3.4"
    
    [tool.poetry.dev-dependencies]
    pytest = "^5.2"
    
    [build-system]
    requires = ["poetry-core>=1.0.0"]
    build-backend = "poetry.core.masonry.api"
    ```
    - The project `dependencies` clearly specify the versions that are required to run this project
    - The `dev-dependencies` specify additional dependencies that are required when running the test suite (i.e. when running `poetry run pytest tests/`)

### Notebook workflow with Poetry

- Activate the virtual environment
    - The easiest way to activate the virtual environment is to create a new shell with `poetry shell`
        - Run `poetry shell` in your Terminal to create a subshell within the virtual environment
        - This is the key step that lets you run a Jupyter notebook with all the right project dependencies
    - To deactivate the virtual environment and exit this new shell type `exit`
    - To deactivate the virtual environment without leaving the shell use `deactivate`.
- Run `jupyter notebook` in Terminal to open the project with Jupyter in your browser
    - Sometimes it’s more confortable to open Jupyter notebooks in VSCode than in web browsers. In VSCode, you can select your preferred kernel without any additional commands
    - Click the "Python" button located near the bottom left corner and select the Python interpreter path
    ![vscode-1](https://hippocampus-garden.com/static/1af05e936dd0b0a7fe84013ef0969630/8ff5a/2021-08-11-10-37-17.png){max-width: 300px, display: block, margin: 0 auto}
    - When settings are done, the selected interpreter is displayed in the top right corner
    ![vscode-2](https://hippocampus-garden.com/static/dcb93dc4e38179aedf74d60197f23de8/7bc0b/vscode.png){max-width: 300px, display: block, margin: 0 auto}

### Workflow with collaborators

- You can follow the steps outlined above, upload your code to GitHub, so your teammates can clone the repo and run `poetry install` to create an identical development environment on their machine
- When you run this command `poetry install`, one of two things may happen:
    - If the `poetry.lock` file exists, use the exact dependency version specified in the lock file to build the virtual environment
    - If the `poetry.lock` file doesn’t exist, then use the `pypoetry.toml` file to resolve the dependencies, build a lock file, and setup the virtual environment
- If you're ever having trouble with the virtual environment or lock file, feel free to simply delete them and recreate them with `poetry install`. Don't manually modify the lock file or virtual environment.

## Related resources

- [Yury Zhauniarovich | Configuring Python Workspace: Poetry](https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace-p2/)
- [Hippocampus's Garden | How to Setup Jupyter in Pipenv / Poetry](https://hippocampus-garden.com/jupyter_poetry_pipenv/)