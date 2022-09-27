---
id: rq9qu5gxuldewr5zufwmfd6
title: Pyenv
desc: ''
updated: 1652631433574
created: 1652605141936
---
# [Pyenv](https://github.com/pyenv/pyenv)

ref: [jayway](https://blog.jayway.com/2019/12/28/pyenv-poetry-saviours-in-the-python-chaos/), [The Python Corner](https://thepythoncorner.com/posts/2022-05-06-managing-python-versions-with-pyenv/#)

`pyenv` is a python interpreter installation manager. It allows you to install and manage multiple python installations, on the same machine.

Fig. Illustrates the hierarchy that pyenv uses to decide which installed python version to use. Credit: [realpython](https://realpython.com/intro-to-pyenv/)
![pyenv-hierarchy](https://files.realpython.com/media/pyenv-pyramid.d2f35a19ded9.png){max-width: 300px, display: block, margin: 0 auto}

## Setup

See the [pyenv documentation](https://github.com/pyenv/pyenv#installation) for installation methods.

With pyenv installed, you can install any python version that you would like. Depending on which directory you’re in, pyenv will point to your specified python version.

Some example of commands

```python
# See all available python installations.
pyenv install --list

# Install some python versions.
pyenv install  3.7.5
pyenv install  2.7.17
pyenv install  3.8.0

# See all python installations that you have installed.
pyenv versions

# Set the default/global from one of the python versions.
pyenv global 3.8.0

# In the current directory, set the python version. This creates the file .python-version.
pyenv local 2.7.17

# To see which python is currently being used.
pyenv version
```

## Related resources

- [The Python Corner | Managing Python versions with pyenv](https://thepythoncorner.com/posts/2022-05-06-managing-python-versions-with-pyenv/#)
    - [Hacker News](https://news.ycombinator.com/item?id=31326052) discussion