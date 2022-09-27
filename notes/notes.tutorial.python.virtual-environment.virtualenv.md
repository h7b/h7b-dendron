---
id: o7gjll8839muf44tiv70gbl
title: Virtualenv
desc: ''
updated: 1652630123555
created: 1652627665019
---
# [Virtualevn](https://virtualenv.pypa.io/en/latest/)

ref: 
- [Yury Zhauniarovich](https://zhauniarovich.com/post/2020/2020-02-configuring-python-workspace/), [](https://dev.to/bowmanjd/python-tools-for-managing-virtual-environments-3bko)
- [Python Tools for Managing Virtual Environments](https://dev.to/bowmanjd/python-tools-for-managing-virtual-environments-3bko)
- [BogoToBogo](https://www.bogotobogo.com/python/python_virtualenv_virtualenvwrapper.php)

[virtualenv](https://virtualenv.pypa.io/en/latest/) is a Python package that is used to create isolated Python virtual environments. The [virtualenv](https://virtualenv.pypa.io/en/latest/) tool is very similar to [[venv|notes.tutorial.python.virtual-environment.venv]]. Its popularity has led to the addition of [[venv|notes.tutorial.python.virtual-environment.venv]] module to the standard library in Python 3.

The `virtualenv` creates a folder which contains all the necessary executables to use the packages that a Python project would need.

The functionality of these tools is similar. The main difference is that
- with virtualenv you can choose what version of Python interpreter to use during the creation of a virtual environment
- `virtualenv` is generally faster than `python -m venv`
- Tools like `pip`, `setuptools`, and `wheel` are often more up-to-date, cached (hence the performance boost). In virtualenv terms, these are [seed packages](https://virtualenv.pypa.io/en/latest/user_guide.html#seeders)

## Usage

Install using `pipx`

```bash
pipx install virtualenv
```

We only need the `virtualenv` tool itself when we want to create a new environment. Start by changing directory into the root of our project directory, and then use the virtualenv command-line tool to create a new environment. To create a virtual environment in the directory `.venv`

```bash
$ mkdir myproject
$ cd myproject

$ virtualenv .venv
```

In this example, `env` is just the name of the directory we want to create our virtual environment inside. There's a common convention to call this directory `env`, and to put it inside our project directory. But we can put it whatever we like.

![file-tree-example](https://www.bogotobogo.com/python/images/virtualenv/tree.png){max-width: 300px, display: block, margin: 0 auto}

Activate the virtual environment

```bash
source ./venv/bin/activate
```

Once activated, the command prompt should change to be prefixed by the name of the virtual environment directory.

```bash
(.venv) [default command prompt] $
```

To exit the virtual environment, deactivate it.

```bash
(.venv) $ deactivate
```

Install stuff into the virtual environment. Packages and dependencies should be installed, and then you can import and use the package.

```bash
(.venv) $ pip install arrow
```

Destroy a virtual environment

```bash
rm -r .venv
```