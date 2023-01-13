---
id: alp3ynverykxh0i32vbj8m1
title: 'Publish with Obsidian Digital Garden plugin'
desc: 'Publish vault with Obsidian Digital Garden plugin'
updated: 1673580276552
created: 1673572996493
tags: cat.tut
---
# Publish vault with Obsidian Digital Garden plugin

After having played with [[publishing via mkdocs|notes.daily.2023-01-09.mkdocs-pub]], I turn to the [[Digital Garden|notes.tutorial.obsidian-md.plugins.digital-garden]] plugin. Judging by the length of article, I feel relieved since `Digital Garden` is much simpler to configure than the [[notes.tutorial.obsidian-md.plugins.github-publisher]].

## Steps to install and configure with Netlify

1. Create a new repository from [this template](https://github.com/oleeskild/digitalgarden) [^1]. This new repo will be called `trade-bt-odg`
2. Connect my Netlify account to the repo `trade-bt-odg` and deploy via Netlify
    - Retrieve the URL of deployed site in `Domain settings` within Netlify
3. Configure in "Digital Garden" plugin settings
    - [Create a personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) then paste it into the "GitHub Token" field in the plugin configuration menu. Also change "GitHub repo Name", "GitHub Username", "Base URL"
    - I did not choose the new `fine-grained personal access token` as instructed [^2], because it requires an expiry date within 1 year, and I don't want to set an expiry date for this token
4. Create a note called `home-page.md` at the root folder of my Obsidian vault
    - add these two keys into this note's frontmatter
    ```yaml
    dg-publish: true
    dg-home: true
    ```

## How to write notes and then publish?

1. Write note in Obsidian
2. In the note's frontmatter, add the key `dg-publish: true`. This action mark that this specific will be sent to the `trade-bt-odg` repo and then deploy via Netlify
3. <kbd>CTRL + P</kbd> to open `Command Palette` in Obsidian, search for 
    - command `Digital Garden: Publish Single Note` to send only this active note
4. I can also publish notes using the `Digital Garden Publication Center` via command palette or the left-side bar.

## Related

- [digitalgardendocs](https://github.com/oleeskild/digitalgardendocs): the repo of the [plugin documentation page](https://dg-docs.ole.dev)