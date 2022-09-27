---
id: a3mb8vqlwptbmo7el3tdt5f
title: Venv
desc: ''
updated: 1652628996371
created: 1652627732646
---
# [Venv](https://docs.python.org/3/library/venv.html)

ref: [Python Tools for Managing Virtual Environments](https://dev.to/bowmanjd/python-tools-for-managing-virtual-environments-3bko)

The [venv](https://docs.python.org/3/library/venv.html) module and `pip` are usually included in your Python installation. Python's venv module is based on [[virtualenv|notes.tutorial.python.virtual-environment.virtualenv]].

## Usage

To create a virtual environment in the directory `.venv`

```bash
python -m venv .venv
```

Activate the virtual environment

```bash
source ./venv/bin/activate
```

Once activated, the command prompt should change to be prefixed by the name of the virtual environment directory. That `(.venv)` (or whatever you named it) is the sign that you have activated your virtual environment. It will not stay active after you reboot your machine or launch a different shell or terminal tab.

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