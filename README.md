# Blog - mes belles lettres

This repo contains the source code of my personal blog and notes.

Current build:
- this static site is published using [Dendron](https://www.dendron.so/), deployed on [Netlify](https://www.netlify.com/)
- articles are plain *Markdown* files located in the `vault` directory, inside a GitHub repo
- each *Markdown* file has a *yaml* frontmatter for storing metadata
- the URL for each note is determined by the `id` key in the `frontmatter`.