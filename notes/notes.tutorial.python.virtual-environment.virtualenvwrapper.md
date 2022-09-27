---
id: 839n1pguofbfmcyyull5chx
title: Virtualenvwrapper
desc: ''
updated: 1652751507257
created: 1652604401624
---
# Manage Virtual Environments with [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/)

[virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/) is a set of extensions to [[virtualenv|notes.tutorial.python.virtual-environment.virtualenv]] tool. The extensions include wrappers for creating and deleting virtual environments and otherwise managing our development workflow, making it easier to work on more than one project at a time without introducing conflicts in their dependencies.

## Why virtualenvwrapper over other tools?

Some features of [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/) are that it:
- Organizes all of your virtual environments in one location
- Provides methods to help you easily create, delete, and copy environments
- Provides a single command to switch between environments. It's just
    ```python
    workon projectname
    ```
    rather than
    ```python
    source ~/Projects/flashylights-env/bin/activate
    ```
- Instead of having a `venv` directory inside or alongside your project directory, `virtualenvwrapper` keeps all your environments in one place: `~/.virtualenvs` by default

## Install `virtualenvwrapper`

### On Windows 10, WSL2 Ubuntu

Prerequisite: [[Enable the Windows Subsystem for Linux (WSL)|notes.tutorial.windows-subsystem-for-linux]]

1. Check if Python was installed in this WSL  
    ```bash
    python3 -V
    ```
2. Download [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/)
    ```bash
    sudo pip3 install virtualenvwrapper
    ```
3. Edit my shell's RC file (e.g. .bashrc, .bash_profile, or .zshrc) and adding the following lines
    ```bash
    # setup script for virtualenvwrapper
    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
    export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
    source /usr/local/bin/virtualenvwrapper.sh
    WORKON_HOME=$HOME/.virtualenvs
    PROJECT_HOME=$HOME/projects
    ```

### On Windows 10
1. I use this [answer](https://stackoverflow.com/questions/20979474/how-can-i-set-environment-variable-workon-home-for-virtualenvwrapper-win/56120236#56120236) to define the `WORKON_HOME` and `PROJECT_HOME` environment variables in Win 10.
    ```shell
    [Environment]::SetEnvironmentVariable("WORKON_HOME", "D:\Workspace\.virtualenvs", "User")
    [Environment]::SetEnvironmentVariable("PROJECT_HOME", "D:\Workspace\project", "User")
    ```

## Use `virtualenvwrapper`

Display the location of `$WORKON_HOME` that contains all of the virtualenvwrapper data/files
```shell
$ echo $WORKON_HOME
```

[mkvirtualenv](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#mkvirtualenv)  
create and activate a new environment in the directory located at `$WORKON_HOME`
```shell
$ mkvirtualenv my-new-project
```

[deactivate](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#deactivate)  
stop using that environment
```shell
(my-new-project) $ deactivate
```

[workon](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#workon)  
List all working virtual environments
```shell
$ workon
```
Activate the desired environment
```shell
$ workon project-name
```

### Specify project directory

ref: [Adam Lombard](https://dev.to/adamlombard/easy-python-specify-a-project-directory-with-virtualenvwrapper-280h)

If you're using `virtualenvwrapper` to manage your Python environments, you can specify your project directory in your environment settings. Doing so will automatically `cd` you into your project when you open its environment — a nice little time-saving feature.

So how:
- When creating our environment, we can use the `-a` flag to specify the project directory:
    ```shell
    $ mkvirtualenv -a [/path/to/project] [name-of-environment]
    ```
- if we've already created a project and environment without this setting? In that case, we can use `setvirtualenvproject` to change this setting
    ```shell
    $ setvirtualenvproject [/path/to/environment] [/path/to/project]
    ```