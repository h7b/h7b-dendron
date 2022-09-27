---
id: g3r6x8hiqtydjxfgk9n4cpq
title: Dataview
desc: ''
updated: 1647570080399
created: 1647568114967
---
# Dataview plugin

Dataview is a [plugin](https://github.com/blacksmithgu/obsidian-dataview/) that treat your Obsidian Vault as a database from which you can query.

## How to index
ref: [Dataview Docs](https://blacksmithgu.github.io/obsidian-dataview/data-annotation/)

You can add `dataview fields` in 2 ways
- in frontmatter
  - syntax: `Key: Value`
- as inline fields
  - format: `Key:: Value` or `[Key:: Value]`
  - notice the double colon (`::`) vs single colon (`:`) as in frontmatter

## Dataview Query Language (DQL)
ref: [Dataview Docs](https://blacksmithgu.github.io/obsidian-dataview/data-queries/)

The DQL is a simplistic, SQL-like language for quickly creating views.

You create dataview queries using `dataview-annotated` codeblocks.

Example query, which show all games in the "game" folder, sorted by "rating", with some metadata:

```
    ```dataview
    TABLE time-played, length, rating
    FROM "games"
    SORT rating desc
    ```
```

If the field name has spaces, punctuation, or other non-letter/number characters, then you can refer to it using Dataview's simplified name, which is all lower case with spaces replaced with hyphen (`-`). For example, 
- "this is a field" becomes *this-is-a-field* 
- "Hello!" becomes *hello*

## Tips

1. In frontmatter (format name: value) and in inline-field (format name:: value) you can write a long paragraph (multiple lines) without problem
    - A paragraph is a group of continuous sentences, without line breaks
    - You can *simulate* multiple paragraphs by using the html tag `<br>` as newline break
    - [Discussion in Obsidian forum](https://forum.obsidian.md/t/dataview-aggeregate-bigger-chunks-of-text-more-than-one-line/22612)

2. Use Dataview inline field as a tag to consolidate information from multiple notes
    - [Discussion in Obsidian forum](https://forum.obsidian.md/t/reverse-block-reference-possible/22445/4)
