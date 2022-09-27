---
id: qvacktliy1b7kqnigmvewo1
title: Workflow
desc: Typical workflow of Obsidian users
updated: 1662330470662
created: 1647820438689
---
# Typical workflow of Obsidian users

## Project note by `@zsviczian`

- Explanation clip on [Youtube](https://www.youtube.com/watch?v=qIKg_1FNUgk)
- Scripts on [GitHub](https://gist.github.com/zsviczian/fd3fcae4e2c4fa2be668756dca59da06)
- Thoughts: 
    - author has interesting way to transclude tasks, working notes, contacts from daily notes into topic and project
    - he uses [Templater](https://silentvoid13.github.io/Templater/) script to achieve some task automation

## Create link to local files/folder

- I can create a markdown link to a file or folder on my local system by holding `CTRL` and drag-drop the file/folder into Obsidian active note

## Use dataview to create connection from daily-note to person-note

- workflow by `dryice` in [Obsidian discord](https://discord.com/channels/686053708261228577/744933215063638183/972992393123102730)
- dataview query
    ````
    ```dataview
    TABLE 
        WITHOUT ID
        link(Source, dateformat(date(Source), "EEE d MMM yy")) as Date___, 
        rows.Comments as "Comments"
    FROM "Journal Folder"
    WHERE  contains(cmnt, this.file.name)
    FLATTEN cmnt as Comments
    WHERE contains(Comments, this.file.name)
    GROUP BY file.link as Source
    SORT rows.file.day desc
    ```
    ````
- demo: ![person-note](https://media.discordapp.net/attachments/744933215063638183/972992392368095252/unknown.png?width=1416&height=670){max-width: 300px, display: block, margin: 0 auto}

## Create a movie database

- [workflow](https://minimal.guide/Guides/Create+a+movie+database) by [`@kepano`](https://twitter.com/kepano) author of [Minimal theme](https://github.com/kepano/obsidian-minimal) for Obsidian
- required other plugins
    - [Minimal Theme Settings](https://github.com/kepano/obsidian-minimal-settings)
    - [Dataview](https://blacksmithgu.github.io/obsidian-dataview/)
    - [Quickadd](https://github.com/chhoumann/quickadd)
    - [Sortable](https://github.com/alexandru-dinu/obsidian-sortable)
- demo: ![minimal-theme](https://user-images.githubusercontent.com/10565871/148671516-348f2b48-440c-484b-8dc2-27006879a1a7.png){max-width: 300px, display: block, margin: 0 auto}

## Retrieve annotations for Hypothes.is via Templater plugin (Hypothes.idian)

ref: [Obsidian Community](https://forum.obsidian.md/t/retrieve-annotations-for-hypothes-is-via-templater-plugin-hypothes-idian/17225)

demo: [youtube](https://youtu.be/f-mVj_DSaag)

This script uses the Templater template.

Template File: [Templater script hosted on GIST GitHub](https://gist.github.com/tfthacker/c48bca69f1520deed0ecbc8840f6241a)

Note: Can use this site to upload and annotate any local document: https://docdrop.org/