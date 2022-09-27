---
id: DgpESplxOc3FCyUunecEw
title: Mkdocs Publish Obsidian
desc: ''
updated: 1650143238579
created: 1639879650950
---
# Use MkDocs to publish my Obsidian vault

## Overview:

Workflow: 
- Write notes in Obsidian
- Prepare files to publish with [MkDocs](https://www.mkdocs.org/)
- Deploy in GitHub Pages or any static site hosting (like [Render](https://render.com/), [Netlify](https://www.netlify.com/), [Vercel](https://vercel.com/))
- or use [Obsidian To Mkdocs | Obs2mk](https://github.com/Mara-Li/mkdocs_obsidian_publish) python script to publish obsidian's note with mkdocs
    
Discussion of workflow in Obsidian forum
- [My Obsidian & Mkdocs workflow](https://forum.obsidian.md/t/my-obsidian-mkdocs-workflow/24424)
- [Obsidian Mkdocs : A free Publish Alternative WorkFlow](https://forum.obsidian.md/t/obsidian-mkdocs-a-free-publish-alternative-workflow/29540)

Showcase: [Tarek Shehata](https://tarekshehata.github.io/alkashi/Math/Basic%20Shapes/Circle/), [Mara-Li](https://mara-li.github.io/mkdocs_obsidian_template/)

Thoughts:
- My 2nd favorite if I need to publish my Obsidian vault
- has dark theme, built-in navigation bar, search feature, `Next` and `Previous` UI links at the end of each doc page, support `mermaid.js` diagram using [mkdocs-mermaid2-plugin](https://github.com/fralau/mkdocs-mermaid2-plugin)
- open source, static site generator, documents are markdown md files
- has [guide](https://squidfunk.github.io/mkdocs-material/setup/adding-a-comment-system/) to integrate [[3rd party comment system|notes.tutorial.comments-static-site]]
- Suitable for technical project documentation.
- mkdocs-material support tags in notes only in [Insider tier](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/)
- mkdocs-material has native support for diagrams with `mermaid.js` in [Insider tier](https://squidfunk.github.io/mkdocs-material/reference/diagrams/0)
- mkdocs-material has [Insider sponsorship](https://squidfunk.github.io/mkdocs-material/reference/diagrams/) starting at USD 10 / month.

## Related resources:

Tutorial:
- Current best tutorial that I used: [Obsidian Mkdocs : A free Publish Alternative WorkFlow](https://forum.obsidian.md/t/obsidian-mkdocs-a-free-publish-alternative-workflow/29540)
- [Starfall Projects | Create multiple websites from one Obsidian vault](https://www.starfallprojects.co.uk/posts/obsidian-monorepo/)
- [the-penguin-book-mkdocs | GitHub | Tutorial to publish notes with mkdocs](https://github.com/Tomodachi94/the-penguin-book-mkdocs/blob/main/README-MKDOCS.md)
- [Publish your Obsidian Notes | GitHub](https://github.com/jobindj/obsidian-publish-mkdocs)
- [free-lightweight-obsidian-publisher | GitHub](https://github.com/PabloLION/free-lightweight-obsidian-publisher)

Showcase:
- [EuroPython Conference | Documenting with MkDocs | Youtube](https://www.youtube.com/watch?v=0pYN6Z-t1-s)
- [Steve Martinelli | 5 Features I Like About Material for MkDocs](https://www.stevemar.net/five-things-about-mkdocs/)

Tools:
- Current 2nd best option: [Mkdocs Obsidian template | GitHub](https://github.com/Mara-Li/mkdocs_obsidian_template)
- [A Material Design theme for MkDocs | GitHub](https://github.com/squidfunk/mkdocs-material)
- [obsidian-export | GitHub](https://github.com/zoni/obsidian-export), CLI program and a Rust library to export an Obsidian vault to regular Markdown
- [mkdocs-static-i18n | GitHub](https://github.com/ultrabug/mkdocs-static-i18n)
- [GruvDoc | GitHub](https://github.com/aasmpro/gruvdoc)