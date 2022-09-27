---
id: bh953lNw4PqewrPxW3pLj
title: My Config Yaml
desc: ''
updated: 1640110187270
created: 1640065902749
---
# What did I configure in my dendron.yml

Dendron use `dendron.yml` file to hold configurations of the workspace

## Dendron - My Configuration per Worspace

Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html)

All of the properties mentioned below need to be created/modified in `dendron.yml` which is accessed via `Ctrl + Shift + P` then `Dendron: Configure (yaml)`
- `useFMTitle: false`<br>
    Set to `false`, not use frontmatter as title when publishing and in the preview<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html#usefmtitle)
- `hierarchyDisplayTitle: "Read more ⬇️"`<br>
    Change the title for children links in published sites from `Children` to `Read more ⬇️`<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html#hierarchydisplaytitle)
- ~~`workspaceVaultSync: sync`<br>
    Enable sync notes using command `Dendron: Workspace: Sync`<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/c4cf5519-f7c2-4a23-b93b-1c9a02880f6b.html#workspace-sync)~~
- Replace `workspaceVaultSync: sync` (previous item) by using [per-vault configuration](https://wiki.dendron.so/notes/6682fca0-65ed-402c-8634-94cd51463cc4/#sync)  
    reason: `workspaceVaultSync: sync` will be deprecated (ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1/#workspacevaultsync))

## Dendron - Configuration per Site
All of the properties mentioned below need to be created/modified in `dendron.yml`, under `site` property

- `siteUrl: {username}.github.io`<br>
    Since I am publishing with GitHub pages, the URL will be `https://{username}.github.io/{notes}/`
- `siteLastModified: true`<br>
    Show a last modified at the bottom of your site
- `gh_edit_link: true`<br>
    Show a `Edit this page on GitHub` link at the bottom of the page
- `gh_edit_view_mode: edit`<br>
    Bring the user directly into editing mode, when they click on `Edit this page on GitHub` link
- `gh_edit_repository: "https://github.com/h7b/h7b.github.io"`<br>
    Add the URL my page's GitHub repository  
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#gh_edit_repository)
- `gh_edit_branch: main`<br>
    Set the branch `main` that my GitHub Pages site is served from
- `title`<br>
    Name of page
- `description`<br>
    Short description of what this page is about
- `author`<br>
    Author of published notes
- `duplicateNoteBehavior`<br>
    I remove this property since I don't intend to use or publish multi-vault scenario
- `mermaid`<br>
    Enable [[mermaid.js | notes.tutorial.mermaid-js]] support to create diagrams<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/ba97866b-889f-4ac6-86e7-bb2d97f6e376.html#diagrams)
- `useKatex`<br>
    Enable Katex support to render Math equations
- `publishByDefault`<br>
    ```yaml
    config:
        blog:
            publishByDefault: false
    ```
    Setup Dendron to only publish notes within the hierarchy `blog` that have `published: true` property in notes' frontmatter<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/c93938a4-0938-49d0-aca2-00e624793650.html)
- `logo`<br>
    Add a logo image for all headers<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#logo-optional)
- `siteFaviconPath`<br>
    Set path to favicon<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#sitefaviconpath-optional)

## Dendron - Configuration per note
- `blog` frontmatter
    - `published: true`
        Set to publish the `blog` page
    - `nav_order: 2`<br>
        Denote order that `blog` appears after `root` in the published nav bar. `root` has `nav_order: 1` by default.
    - `has_collection: true`<br>
        Set `blog` as a collection, which doesn't have a table of contents (children links)
    - `sort_by: date`
        Sort items in `blog` collection page, by created date
    - `sort_order: reverse`<br>
        Sort items in `blog` collection page, by descending order
- `notes` frontmatter
    - `nav_order: 3`<br>
        Denote order that `notes` appears after `blog` in the published nav bar
    - `reading` frontmatter
        - `nav_order: 1` <br>
            Denote order that `reading` appears 1st as children of `notes` in the published nav bar
    - `tutorial` frontmatter
        - `nav_order: 2` <br>
            Denote order that `tutorial` appears in 2nd order as a children node of `notes` in the published nav bar
    - `finance` frontmatter
        - `nav_order: 3`
    - `news` frontmatter
        - `nav_order: 4`
- blog articles frontmatter
    - `published: true`<br>
        Set the published status of each article. `true` means the article is published
    - `excerpt: 'expample_content'`<br>
        Set an `example_content` to be displayed as excerpt of each blog articles in the `blog` collection<br>
        Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#excerpt)
