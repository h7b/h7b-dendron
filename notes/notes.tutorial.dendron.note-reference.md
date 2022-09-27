---
id: Hs0V11FbDMMurMrFArdkC
title: Note Reference
desc: ''
updated: 1663347658408
created: 1636948922923
---
# How to reference content from other notes and embed them in your current note (transclusion)

ref: [dendron wiki](https://wiki.dendron.so/notes/f1af56bb-db27-47ae-8406-61a98de6c78c/)

Currently, Dendron supports 4 types of references to help you control the amount of content that gets embedded:
- note references
    - syntax: `![[name.of.note]]`
- header references
    - syntax: `![[name.of.note#header]]`
- block references
    - syntax: `![[name.of.note#^important-paragraph]]`
- range references
    - syntax: `![[name.of.note#starting-header:#ending-header]]`

## Additional Options

### Line Offset
You can use line offsets to skip a number of lines when using a header reference. The syntax is `,{number}`. 

Example of using a note reference offset to offset an initial heading, skipping the actual header when doing the embedding.

`![[demo.embed.block#head1,1]]`

### Wildcard Headers as a Range Boundary

For example, the following would reference the content from header1 to the next header.
`![[demo.embed.block#head1:#*]]`

Update 2022-09-16, from v0.103 this behavior is set by default with the new setting value [enableSmartRefs](https://wiki.dendron.so/notes/65h7pdzxe43tupzsvik9sf1/). So we don't need to add `:#*` into the note reference to transclude everything from the given header to the next header of equal or lesser depth.