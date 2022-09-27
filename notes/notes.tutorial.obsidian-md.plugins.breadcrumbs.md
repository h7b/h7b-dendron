---
id: pLRYz6BnANNzAcmFyZ8ap
title: Breadcrumbs
desc: ''
updated: 1654392172955
created: 1640942481973
---
# Breadcrumbs

- GitHub: https://github.com/SkepticMystic/breadcrumbs
- demo ![breadcrumbs](https://user-images.githubusercontent.com/70717676/123402846-75a67f80-d5a8-11eb-8230-75c37441f122.png){max-width: 300px, display: block, margin: 0 auto}

## Use Breadcrumbs plugin to navigate the hierarchical notes in Dendron vault

With a recent patch to v2.9.1, the [Breadcrumbs plugin](https://github.com/SkepticMystic/breadcrumbs) now can be used to navigate the hierarchy of notes in Dendron vault. 
Here is the screen cap from mobile ios. As in the photo, on the right pane, `up` means go back to parent of current active note. Looks awesome. 
![breadcrumbs-ios](https://i.imgur.com/cNwupI1.png){max-width: 300px, display: block, margin: 0 auto}

Now Obsidian with Breadcrumbs plugin is great to read and edit Dendron notes on mobile. 

Then a problem now is how to include only `.vault` folder of Dendron into a vault folder of Obsidian, so the icloud sync for Obsidian is not flooded by the swarms of files in` .next` folder of Dendron

I need only the *Breadcrumbs* plugin for Obsidian to navigate the hierarchy structure of Dendron notes, without modifying the frontmatter of each notes.

**Update 2021-12-31:**

The situation is even better after I used the [[Netlify publishing workflow|notes.tutorial.dendron.publish-netlify#publish-my-dendron-vault-using-netlify]]. My dendron folder now is not flooded by thousands of files from `node_modules` and `.next` folder. So I can put my Dendron folder directly inside an iCloud Drive folder to sync with my iPhone. 

From there I can open, edit and navigate the hierarchy structure of my Dendron vault using Obsidian on iOS

This is basically a game changer workflow for me. It means that I can edit my Dendron vault on the fly on mobile. When I’m on desk, the change will sync to my laptop via iCloud. Then i open Dendron workspace to push changes to GitHub repo. Done. My notes are published. So great

**Update 2022-04-01:**

*Breadcrumbs* has its own [codeblocks](https://breadcrumbs-wiki.onrender.com/docs/Codeblocks). I use it to display the hierarchical tree view of notes in Dendron-hierarchy format, by inserting the breadcrumbs codeblock into a specific note.

````
```breadcrumbs
type: tree
dir: down
```
````

## Related resources

- [Obsidian Hub | Breadcrumbs Quickstart Guide](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/Breadcrumbs+Quickstart+Guide)