---
id: jxv1ptNuKOtO6aUhTFCGt
title: Thoughts on Markdown
desc: ''
updated: 1647564453722
created: 1645557747998
---
# Reading 2022-02-22

## Metadata

- Ref:: [Smashing Magazine](https://www.smashingmagazine.com/2022/02/thoughts-on-markdown/)
- Title:: Thoughts On Markdown
- Author:: Knut Melvær
- Year of publication:: 2022
- Category:: Blog
- Topic::
- Related::
  - [Hacker News | Thoughts On Markdown](https://news.ycombinator.com/item?id=30395130)
  - [Hacker News | Compare AsciiDoc to Markdown](https://news.ycombinator.com/item?id=27744509)
  - [Hacker News | Plaintext Productivity](https://news.ycombinator.com/item?id=30745524)
  - [Reddit | Markdown vs Asciidoc](https://www.reddit.com/r/technicalwriting/comments/qxcsx6/markdown_vs_asciidoc/)
  - [MyST - Markedly Structured Text](https://myst-parser.readthedocs.io/en/latest/)
  - [Dendron discussion](https://github.com/dendronhq/dendron/discussions/2347#discussioncomment-2277719)
  - [Org Mode Is One of the Most Reasonable Markup Languages to Use for Text](https://karl-voit.at/2017/09/23/orgmode-as-markup-only/)

## Notes from reading

[Compare AsciiDoc vs Markdown](https://docs.asciidoctor.org/asciidoc/latest/asciidoc-vs-markdown/)

Markdown: 
- was created to make the source readable
- was an attempt to take all of those community-accepted formatting conventions and standardize it into a single format
- is a formalisation of conventions which were in common in email & news long before HTML even existed

The main advantages of AsciiDoc:
- more flexible/powerful formatting options
- letting you implement a ton of structural/metadata type stuff with a syntax that is more complicated than Markdown but far simpler than XML

MyST - Markedly Structured Text:
- extending CommonMark to merge with a lot of the strengths from reStructuredText
- implement [directives](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html#directives-a-block-level-extension-point) in Markdown as a standard format for special properties to things like images, admonitions, and for entry points for plugins to integrate well directly within the Markdown