---
id: hUaRNec8EuScPxslyPKQw
title: Periodic Daily Notes
desc: ''
updated: 1652338678958
created: 1643923735587
---
# How to organize Daily notes in Obsidian?

> Note to self: I use multiple files in one folder. Since I don't write daily journal much, I can't experiment the advantages of these methods.

## Organized in nested folders
ref: [blog.mjb.im](https://blog.mjb.im/nested-daily-note-folders-in-obsidian)

If you use the `Daily Notes` or `Periodic Notes` plugins for Obsidian, and you hate that it creates all of the files in one giant folder, you can clean it up by telling Obsidian to create intelligently nested folders by year, month, date or whatever else you’d like.

Opening the settings for the `Daily Notes` plugin, you can predefined the file format and a whole file path.

![config-example](https://i.snap.as/N3N6CBBu.png){max-width: 300px, display: block, margin: 0 auto}

For example, if you configure `YYYY/MM-MMMM/YYYY-MM-DD`, the `Daily Notes` plugin will create your daily note in a nested folder structure that includes the year and month
```text
2022/
  01-January/
    2022-01-01.md
    2022-01-02.md
    ...
  02-February/
    2022-02-01.md
    2022-02-02.md
    ...
```

## Organized in one massive file
ref: [Obsidian forum](https://forum.obsidian.md/t/one-single-massive-daily-note-instead-of-a-note-per-day/31660), [Jamie Todd Rubin](https://jamierubin.net/2022/01/25/practically-paperless-with-obsidian-episode-15-daily-notes-as-an-index-to-my-life/)

There's a second approach that prefers using 1 large file for all of daily notes. 

Their arguments:
- better navigation
- avoid noise in graph view in Obsidian
- following a consistent convention of keyword, with search feature, they find easier to pull aggregated information out