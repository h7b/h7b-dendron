---
id: je305k3anf8963hj4dcrzka
title: Static Dataview Table
desc: ''
updated: 1662332681413
created: 1662331329887
---
# Turn your dataview table into a static standard table

ref: [forum.obsidian](https://forum.obsidian.md/t/dataviewjs-snippet-showcase/17847/225?u=ryanjamurphy)

The trick is to use a templater template for your dataviewjs code.

Example: need to publish a static simple table that gets its pages from "a Folder, tagA and not tagB", where a [[dataview|notes.tutorial.obsidian-md.plugins.dataview]] field contains "a keyword". For context, it is used to get a list of films (markdown files located in folder "Films") that I have but haven’t seen yet (does not have tag `#saw`) that are on my wishlist (have tag `#wishlist`) for the next Criterion Blu-ray sale (in frontmatter, there is a field named "edition" which contains the keyword "Criterion").

Put this code into the template.

```javascript
<%*
const headers = ["File", "file.folder"];
const tableValues = DataviewAPI.pages('"Films" and -#saw and #wishlist')
.where (p => p.edition.includes("Criterion"))
.sort(p => p.file.name, 'asc')
.map(p =>[p.file.link, p.file.folder]);
const myTable = DataviewAPI.markdownTable(headers, tableValues);
-%>
<% myTable %>
```

Then apply this template to a file. Result.

![static-table](https://forum.obsidian.md/uploads/default/original/3X/6/c/6c859887f3b71697834e1b4b138d1050c6836fc9.png){max-width: 300px, display: block, margin: 0 auto}