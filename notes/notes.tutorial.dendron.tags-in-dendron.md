---
id: InFDySxriICCHyN51z9g2
title: Tags in Dendron
desc: ''
updated: 1642616199784
created: 1642614079563
---
# How do I use tag in note taking

## How tag is implemented in Dendron
ref: [Dendron wiki](https://wiki.dendron.so/notes/8bc9b3f1-8508-4d3a-a2de-be9f12ef1821/)

Tags can be added either 
- inline as a hashtag 
- or in the `frontmatter` of each note  
    example:
    ```text
    tags:
    - my.example
    - other.one
    ```
    or 
    ```text
    tags: [my.example, other.one]
    ```

A hashtag is any string (excluding spaces, quotation marks, question marks) following `#` (eg. `#example.my-example`)

In Dendron, tags are just a shorthand for writing notes with aliases `[[#example.my-example|tags.example.my-example]]`. The benefits of this approach can be listed as follows.
- I can personalize each tag's color by configuring the `color` key in the frontmatter of each tag's note
- use commands like Rename Note or Refactor Hierarchy to rename or reorganize your tags, and it will update all notes where these tags were used
- add content to your tag and it will show up when you hover over the tag in the editor, or when you publish it
- organize your tags into hierarchies (like `#cuisine.ethiopian` and `#cuisine.swedish`)
- can link tags together by adding links in their note's content

Tags support press `Tab` to autocomplete `(intellisense)`, but tag notes must be created for autocomplete to work. To create a tag note, select the tag and use command `Dendron: Goto Note` (or `Ctrl+Enter`).

## What kind of tag do I use?

Some typical tags mentioned in a [discussion in Obsidian community](https://forum.obsidian.md/t/a-process-for-figuring-out-what-organizational-tags-i-need-in-my-vault/31221)
