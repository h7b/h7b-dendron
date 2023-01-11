---
id: 8scrji4wa1nwmrz4a0vosim
title: Publish vault with Obsidian Github Publisher
desc: 'Publish vault with Obsidian Github Publisher'
updated: 1673413237586
created: 1673404028262
tags: cat.tut
---
# Publish vault with mkdocs

## Steps to install and configure

1. Click [here](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/generate) to create a new repository from [this template](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/) [^1]. This new repo will be called `trade-bt-mkdocs`
2. Configure in "GitHub Publisher" plugin settings
    - [Create a personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) then paste it into the "GitHub Token" field in "GitHub Configuration" tab. Also change "Repo Name", "Github Username"
    - I did not choose the new `fine-grained personal access token` as instructed [^2], because it requires an expiry date within 1 year, and I don't want to set an expiry date for this token
    - In "Plugin Settings" tab, 
        - change "Share Key" to `dg-publish`. Reason: I want to use the same publishing keyword with [[notes.tutorial.obsidian-md.plugins.digital-garden]]
        - change "Excluded Folder" to `99_template`. Reason: I don't need to publish any notes within this folder
    - In "Upload Configuration" tab,
        - set "Folder behavior" to `Obsidian Path`. I want to replicate the folder structure of Obsidian vault to the published site [^3]
        - set "Default folder" to `docs/notes`
3. Close and reopen Obsidian to assure that the changes are executed. Because I also encounter the same error as this user's [issue](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4599564)
4. Configure the file `mkdocs.yml` in the repo `trade-bt-mkdocs`
    - add the [Navigation footer](https://squidfunk.github.io/mkdocs-material/setup/setting-up-the-footer/#navigation) to include links to the previous and next page of the current page
5. Connect my Netlify account to the repo `trade-bt-mkdocs` and deploy via Netlify. Read the [tutorial in details](https://obsidian-publisher.netlify.app/getting%20started/publishing/) to learn how to deploy
6. Since I deploy via Netlify, I have to modify the `requirements.txt` as discussed at [here](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4608415)
    - Change: `obsidiantools==0.10.0` -> `obsidiantools==0.8.1`. Reason: Netlify only support python 3.8

[^1]: https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template
[^2]: https://dg-docs.ole.dev/advanced/fine-grained-access-token/
[^3]: https://obsidian-publisher.netlify.app/obsidian/#upload-configuration

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