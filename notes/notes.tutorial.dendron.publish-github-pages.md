---
id: pgOwGoZMrf42FwD57muPj
title: Publish GitHub Pages
desc: ''
updated: 1642549513542
created: 1640065640233
---
# Publish Dendron vault using Github Pages with GitHub Actions
ref: [Dendron wiki](https://wiki.dendron.so/notes/FnK2ws6w1uaS1YzBUY3BR/)

According to the [pricing page](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions), the current limit of free plan is 2000 build minutes per month with GitHub Actions vs [300 build minutes](https://www.netlify.com/pricing/) of Netlify.

## Getting started

1. Signup [GitHub](https://github.com/)

2. Generate a new Dendron Workspace pre-configured for GitHub Pages with GitHub Actions by cloning this [template](https://github.com/dendronhq/template.publish.github-action) into my GitHub repo  
    I created a repo name: `h7b-dendron-gh-pages-action`

3. Install dendron-cli
    ![[notes.tutorial.dendron.publish-github-pages.outdated-version#install-dendron-cli,1:#*]]

4. Configure Git on local machine
    ![[notes.tutorial.dendron.publish-github-pages.outdated-version#configure-git-on-my-laptop,1:#*]]

5. Setup GitHub Pages
    - Create a `gh-pages` branch
      ```shell
      git checkout -b gh-pages
      git push -u origin HEAD
      ```
    - Choose publishing source for the `gh-pages` branch by following the [GitHub guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
    - Switch back to `main` branch
    ```shell
    git checkout main
    ```
6. Configure Dendron on local machine
    - Add parameter `siteUrl` into `dendron.yml`, where the value of param `siteUrl` will be `{username}.github.io`
    - Add parameter `sync: sync` into  `dendron.yml` so I can use the command `Dendron: Workspace: Sync` to push changes to GitHub repo instead of relying on terminal.
    ```yaml
    vaults:
        -
            fsPath: vault
            name: h7b-dendron-gh-pages-action
            sync: sync
    ```
7. Configure custom domain name if needed
    - Follow the [GitHub guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)
    - Add your site `cname` value into the file `.github/workflows/publish.yml`
    - configure the `siteUrl` in `dendron.yml` with my custom domain name

DONE