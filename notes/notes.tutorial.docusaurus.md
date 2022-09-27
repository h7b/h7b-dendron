---
id: I4vsY3q3vnRfMhKb
title: Docusaurus
desc: ''
updated: 1652741021853
created: 1627044913994
---
# Publish documents and blog with Docusaurus

Tutorial `Docusaurus in 5 min` from [Docusaurus](https://tutorial.docusaurus.io/docs/intro)

Introduction docs of `Docuraurus` can be found at [link](https://docusaurus.io/docs)

Playground to test Docusaurus in browser, without installing anything. Read more at [link](https://docusaurus.io/docs/playground)

It is easy to translate a Docusaurus site with its internationalization (i18n) support. Read more at [link](https://docusaurus.io/docs/i18n/introduction)

## Thoughts

My thoughts on Version: 2.0.0-beta.13

Pros:
- generate documents as a Single Page Application (SPA), dark mode
- Has sidebar navigation, menu bar, search bar, admonition, i18n built-in ([crowdin](https://crowdin.com/) plugin or alternative locale markdown files), `Next` and `Previous` UI links at the end of each doc page, tabbed content.
- has url slug in frontmatter to generate a static URL for each md file

Cons:
- when I reorganize the hierarchy structure of md files (ie. move to other folder, rename folder that contains md files, rename md files) in `docs` folder, I need to manually  
    - update doc IDs in my sidebar file, since notes hierarchy structure are hardcoded in sidebar file for sidebar for navigation
    - update the reference links to other markdown files 
- does not support wikilink style, need custom script to convert to markdown link. Or use a [plugin](https://github.com/ozntel/obsidian-link-converter) in Obsidian to convert the link in notes within your vault.

## Related resources

- Tutorial in details by [Zatta Production](https://zatta.link/en/web/docusaurus-how-to.html)
- Tutorial in details by [Danny Chávez](https://github.com/dochavez/Documenting-with-Docusaurus-V2.-)
- Tutorial in details by [LogRocket](https://blog.logrocket.com/easy-documentation-with-docusaurus/)
- Basic tutorial by [Victoria Lo](https://dev.to/lo_victoria2666/build-beautiful-documentation-websites-with-docusaurus-8o2)
- Reason to use Docusaurus by [JavaScript in Plain English](https://javascript.plainenglish.io/10-reasons-to-use-docusaurus-for-your-docs-blog-marketing-site-48dbf2c58b70)
- [Deployment guide](https://docusaurus.io/docs/deployment) from Docusarus.
- Integrate [PostHog analytics](https://posthog.com/) (free alternative of [Plausible](https://plausible.io/)) to Docusaurus v2 site by [Evan Tay](https://evantay.com/blog/docusaurus-posthog/)
- [Fathom analytics plugin](https://github.com/pradel/docusaurus-plugin-fathom) for Docusaurus v2

## Getting started

What I did step-by-step on my Windows 10 machine.

1. Open terminal, go to the local folder of my workspace
    ```shell
    cd .\my_workspace\
    ```
2. create a new Docusaurus site named `datadiva-docusaurus` with theme `classic`
    ```shell
    npx create-docusaurus@latest datadiva-docusaurus classic
    ```
    Result: a new folder `datadiva-docusaurus` will be created inside `my_workspace`
3. Login to my GitHub profile, create a new repo called `datadiva-docusaurus` 
4. Open terminal, go to folder `datadiva-docusaurus`
    ```shell
    cd .\my_workspace\datadiva-docusaurus
    ```
5. Initialize git
    ```shell
    git init
    ```
6. Add all files in current working folder and all other directories recursively that are not specified in the `.gitignore` to git
    ```shell
    git add .
    ```
7. Commit the change
    ```shell
    git commit -m "first commit"
    ```
8. Create the branch `main`
    ```shell
    git branch -M main
    ```
8. Connect my GitHub repo with my computer
    ```shell
    git remote add origin git@github.com:h7b/datadiva-docusaurus.git
    ```
9. Push changes from my local working folder to my remote repo
    ```shell
    git push -u origin main
    ```

## Deploy my Docusaurus static site on Render

[Render](https://render.com/) free plans [introduction and limitations](https://render.com/docs/free) 

The offical [deployment guide from Render](https://render.com/docs/deploy-docusaurus) is for `Docusaurus v1`. It's not applicable for site created with `Docusaurus v2` like mine.

Step-by-step to deploy my `datadiva-docusaurus` static site on Render:

1. Create a new Static Site on Render, and give Render permission to access your Docusaurus repo
2. I use the following values during creation
    - Name: `datadiva`
    - Build Command: `yarn build`
    - Publish Directory: `build`