---
id: 8scrji4wa1nwmrz4a0vosim
title: Publish with Obsidian Github Publisher
desc: 'Publish vault with Obsidian Github Publisher and mkdocs'
updated: 1673580057483
created: 1673404028262
tags: cat.tut
---
# Publish vault with Obsidian Github Publisher and mkdocs

In a beautiful day, I have interest to publish a trading journal using [mkdocs](https://www.mkdocs.org/). In my setup, I use the [[notes.tutorial.obsidian-md.plugins.github-publisher]] plugin to send the notes written in Obsidian, into a GitHub repository, then deploy on [Netlify](https://www.netlify.com/) and [Cloudflare Pages](https://pages.cloudflare.com/).

## Steps to install and configure 

### with Netlify

1. Click [here](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/generate) to create a new repository from [this template](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/) [^1]. This new repo will be called `trade-bt-mkdocs`
2. Connect my Netlify account to the repo `trade-bt-mkdocs` and deploy via Netlify
    - Retrieve the URL of deployed site in `Domain settings` within Netlify
    - Read the [tutorial in details](https://obsidian-publisher.netlify.app/getting%20started/publishing/) to learn how to deploy
3. Since I deploy via Netlify, I have to modify the `requirements.txt` as discussed at [here](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4608415)
    - Change: `obsidiantools==0.10.0` -> `obsidiantools==0.8.1`. Reason: Netlify only support python 3.8
4. Configure in "GitHub Publisher" plugin settings
    - [Create a personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) then paste it into the "GitHub Token" field in "GitHub Configuration" tab. Also change "Repo Name", "Github Username"
    - I did not choose the new `fine-grained personal access token` as instructed [^2], because it requires an expiry date within 1 year, and I don't want to set an expiry date for this token
    - In "Plugin Settings" tab, 
        - change "Share Key" to `dg-publish`. Reason: I want to use the same publishing keyword with [[notes.tutorial.obsidian-md.plugins.digital-garden]]
        - change "Excluded Folder" to `99_template`. Reason: I don't need to publish any notes within this folder
    - In "Upload Configuration" tab,
        - set "Folder behavior" to `Obsidian Path`. I want to replicate the folder structure of Obsidian vault to the published site [^3]
        - set "Default folder" to `docs`
5. Close and reopen Obsidian to assure that the changes are executed. Because I also encounter the same error as this user's [issue](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4599564)
6. Configure the file `mkdocs.yml` in the repo `trade-bt-mkdocs`
    - change the `site_url` into the valid Netlify link from previous step
    - add the [Navigation footer](https://squidfunk.github.io/mkdocs-material/setup/setting-up-the-footer/#navigation) to include links to the previous and next page of the current page
    - change the [colors](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/)
    - change the [fonts](https://squidfunk.github.io/mkdocs-material/setup/changing-the-fonts/)
    - change the [logo and icons](https://squidfunk.github.io/mkdocs-material/setup/changing-the-logo-and-icons/)
    - (optional) set up the [navigation tree](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/). I didn't do this step. Because i don't want to change manually the items in the navigation tree whenever I change the file structure
    - add a [git repository](https://squidfunk.github.io/mkdocs-material/setup/adding-a-git-repository/)
7. Enable the `Comments` section for specific page only, instead of all page like in [the template](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/)
    - in GitHub repo, path `trade-bt-mkdocs/overrides/`, duplicate the `main.html` as `page_comments.html`. After that, in the note (page) where I want to enable the comments, I will add the key `template: page_comments.html` in its frontmatter. [^4]
    - Read [here](https://squidfunk.github.io/mkdocs-material/reference/?h=template#setting-the-page-template) to understand why the key `template: custom.html` works
    - In this [section](https://squidfunk.github.io/mkdocs-material/customization/#extending-the-theme), the author explain how to extend the `mkdocs-material` using the `custom_dir` setting, what's the meaning of folder `overrides`, `partials`
8. (Optional) Disable the workflow `Building Mkdocs Page` in GitHub Actions [^5], since I deploy solely via Netlify. This only helps the repo status clean. It does not affect on the success of build process.
9. Create a custom front page
    - Follow this [issue](https://github.com/squidfunk/mkdocs-material/issues/1996) and replicate a `home.html` with examples from [up42-py](https://github.com/up42/up42-py/blob/master/docs/theme_override_home/home.html), [le-ref-architecture-doc](https://github.com/binbashar/le-ref-architecture-doc/blob/master/material/overrides/home.html), [mkdocs-material](https://github.com/squidfunk/mkdocs-material/blob/master/src/.overrides/home.html)

[^1]: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template
[^2]: https://dg-docs.ole.dev/advanced/fine-grained-access-token/
[^3]: https://obsidian-publisher.netlify.app/obsidian/#upload-configuration
[^4]: https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/70#discussioncomment-4656676
[^5]: https://docs.github.com/en/actions/managing-workflow-runs/disabling-and-enabling-a-workflow

### with Cloudflare Pages

1. Create a new repository from [this template](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/). This new repo will be called `trade-bt-mkdocs`
2. Connect my Cloudflare account to the repo `trade-bt-mkdocs` and deploy via [Cloudflare Pages](https://pages.cloudflare.com/)
    - Retrieve the URL of deployed site in `Domain settings` within Cloudflare
3. Since Cloudflare Pages support only up to `python 3.7` [^1], i need to modify the file `trade-bt-mkdocs/runtime.txt` from `3.8` to `3.7`. And also modify the `requirements.txt` as in configuration step with Netlify
4. From step 4 through 9, they are similar to the Netlify part.

[^1]: https://developers.cloudflare.com/pages/framework-guides/deploy-an-mkdocs-site/

## How to write notes and then publish?

1. Write note in Obsidian
2. In the note's frontmatter, add the key `dg-publish: true`. This action mark that this specific will be sent to the `trade-bt-mkdocs` repo and then deploy via Netlify
3. <kbd>CTRL + P</kbd> to open `Command Palette` in Obsidian, search for 
    - command `Github Publisher: Share active file` to send only this active note
    - or command `Github Publisher: Upload all shared note` to send all the notes with the key `dg-publish: true`

## Related

- [[notes.tutorial.mkdocs-publish-obsidian]]
- [Obsidian Mkdocs Publisher : A free publish alternative](https://forum.obsidian.md/t/obsidian-mkdocs-publisher-a-free-publish-alternative/29540)
    - in this thread in Obsidian forum, the plugin owner explain her changelog
- [Deploy MkDocs with Material or Material Insiders theme to Netlify](https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-netlify/)
- [Deploy MkDocs with Material or Material Insiders theme to Cloudflare Pages](https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-cloudflare/)
- [Cloudflare Docs | Deploy an Mkdocs site](https://developers.cloudflare.com/pages/framework-guides/deploy-an-mkdocs-site/)