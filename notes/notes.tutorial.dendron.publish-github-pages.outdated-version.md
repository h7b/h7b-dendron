---
id: 4JaNP2kqnpmMjbNSDlkoc
title: Outdated Version
desc: ''
updated: 1642542278645
created: 1642539820851
---
# Publish Dendron vault using Github Pages without GitHub Actions
ref: [Dendron wiki](https://wiki.dendron.so/notes/yg3EL1x9fEe4NMqxUC3jP/)

> Update 2022-10-18: This guide turnS outdated and not recommended anymore, since I need to build the static site locally and push the output manually to GitHub repo. Please use one of these three recommended workflows: [[notes.tutorial.dendron.publish-github-pages]], [[notes.tutorial.dendron.publish-netlify]], [[notes.tutorial.dendron.publish-render]]

## Install dendron-cli

Install dendron-cli to check version of dendron and further experiments<br>
Ref: [Dendron wiki](https://wiki.dendron.so/notes/23a1b942-99af-45c8-8116-4f4bb7dccd21.html)

In order dendron-cli script to work, I need to relax the script execution policies of Windows<br>
Ref: [Link](https://www.roelpeters.be/solved-running-scripts-is-disabled-on-this-system-in-powershell/)

## Configure Git on my laptop
ref: [Dendron Wiki - publish your notes with Github pages](https://wiki.dendron.so/notes/yg3EL1x9fEe4NMqxUC3jP/)

- Configure Git login in VS Code<br>
    ```bash
    git config --global user.name "yourusername"
    git config --global user.email "email@youremail.com"
    ```
    Ref: [Link](https://www.jcchouinard.com/install-git-in-vscode/)
- Create a personal access token and use it to authenticate from VS Code.<br>
    Ref: [GitHub Docs](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)

## Prepare to write 1st note in Dendron
- Create a repo in GitHub named `{username}.github.io`. Hence my personal GitHub Pages will be `{username}.github.io/notes`
- Clone remote repo `{username}.github.io` to local (my laptop). I simply install and use [GitHub Desktop](https://desktop.github.com/) to do this
- Open VS Code > Open Command Palette (`Ctrl + Shift + P`) > Type in `Dendron: Initialize Workspace` > Choose the correct location of my cloned repo, setup from previous step. 
- Start to write 1st note in Dendron.<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/784b8d5e-58eb-4e3e-98b0-8ed1690abc74.html)
- Add property `sync: sync` into  `dendron.yml`  
    ref: [Dendron wiki | per-vault configuration](https://wiki.dendron.so/notes/6682fca0-65ed-402c-8634-94cd51463cc4/#sync)  
    reason: enable Dendron synchronize everything: Dendron will first commit all your changes, then pull changes from the remote, and finally push everything back to the remote
    ```yaml
    vaults:
        -
            fsPath: vault
            name: h7b-blog-dendron
            sync: sync
    ```
- Open Command Palette > Type in `Dendron: Workspace: Sync` to synchronize your 1st note to your GitHub repo. 

## Configure to Dendron settings to publish notes via GitHub Pages

- Turn on GitHub Pages of the created repo `{username}.github.io`
- Add property `SITE_URL` into `dendron.yml`<br>
    `SITE_URL` should be `{username}.github.io`<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/230d0ccf-5758-4a8f-b39b-3b68e1482e2b.html)

## Steps to build and publish notes

1. Export with GitHub target
    ```shell
    npx dendron publish export --target github
    ```
2. First time deploying the change
    ```shell
    git add .
    git commit -m "Dendron page update"
    git push
    ```
3. Next time deploying other changes
    ```shell
    rm -rf docs
    rm -rf .next
    rm -rf node_modules
    rm -rf package*.json
    npm install @dendronhq/dendron-cli@latest
    npx dendron publish init
    npx dendron publish export --target github
    git add .
    git commit -m "Dendron page update"
    git push
    ```

DONE