---
id: A34E5ysMVVDmygigYomiU
title: Data Model behind Notion
desc: ''
updated: 1647563369959
created: 1644496858779
---
# Reading 2022-02-10

## Metadata

- Ref:: [Notion blog](https://www.notion.so/blog/data-model-behind-notion)
- Title:: The data model behind Notion's flexibility
- Author:: Jake Teton-Landis
- Year of publication:: 2021
- Category:: Blog
- Topic:: 

## Notes from reading

Everything you see in Notion is a block. Text, images, lists, a row in a database, even pages themselves — these are all blocks, dynamic units of information that can be transformed into other block types or moved freely within Notion

![block-basic](https://www.notion.so/cdn-cgi/image/format=auto,width=1920,quality=100/https://images.ctfassets.net/spoqsaf9291f/7aiA3EDv0NUB4D6UokLVTU/4d743d0ba925de44ef85684346889643/blocks-2.png){max-width: 300px, display: block, margin: 0 auto}

The content attribute of a block is what stores the array of block IDs (or pointers) referencing those nested blocks

![block-content-id](https://www.notion.so/cdn-cgi/image/format=auto,width=1920,quality=100/https://images.ctfassets.net/spoqsaf9291f/3q05C3cpoP2BwkZ0i4j9lO/25c6a5c9d591b1a6b61349272394b11b/blocks-3.png){max-width: 300px, display: block, margin: 0 auto}