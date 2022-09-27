---
id: 2g2j6hd112b40akel8u7992
title: Mito
desc: ''
updated: 1653180075076
created: 1653179970852
---
# Mito

[Mito](https://trymito.io/) is an extension that enable the Excel-like UI within Jupyter notebook

## Getting started with Mito

ref: [Mito | Install Mito inside a virtual environment](https://docs.trymito.io/getting-started/installing-mito/installing-mito-inside-a-virtual-environment),

Preparation: Install [[virtualenvwrapper|notes.tutorial.python.virtual-environment.virtualenvwrapper#install-virtualenvwrapper]] or any [[alternatives|notes.tutorial.python.virtual-environment]] like [[poetry|notes.tutorial.python.virtual-environment.poetry.jupyter-in-poetry]]

Step-by-step:

1. Create a new virtual environment named `mitoenv`. I used [[virtualenvwrapper|notes.tutorial.python.virtual-environment.virtualenvwrapper]] for this example
    ```shell
    mkvirtualenv mitoenv
    ```
2. install the Mito installer
    ```shell
    pip install mitoinstaller
    ```
3. run the installer
    ```shell
    python -m mitoinstaller install
    ```
    Done here. Jupyter Lab will be called to open in browser.
4. Next time, I can initiate Jupyter lab instance to start, using
    ```shell
    py -m jupyter lab
    ```