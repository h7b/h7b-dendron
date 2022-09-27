---
id: c1-h7c_wOFHJkpzI1t4Gx
title: Dendron
desc: ''
updated: 1652895240701
created: 1625432744672
---
# Write and publish notes using [Dendron](https://www.dendron.so/)

[[Workflow|notes.tutorial.dendron.publish-netlify]] to publish vault by deploying via [Netlify](https://www.netlify.com/) and notes are stored as md files in GitHub private repo.
- My favorite method
- Much better, both in execution time, number of keystroke, size of local folder on disk and manual effort, vs the workflow of [[publishing via GitHub Pages|notes.tutorial.dendron.publish-github-pages]]
- with this Netlify workflow, I just need to push updated contents to GitHub repo with command `Dendron: Workspace: Sync`, and all of the built process will be executed automatically by Netlify.

[[Workflow|notes.tutorial.dendron.publish-github-pages]] to publish vault via GitHub Pages

I use Obsidian on iOS with [[Breadcrumbs plugin|notes.tutorial.obsidian-md.plugins.breadcrumbs]] to view and edit my Dendron vault on iPhone.

An illustration that helps me to understand the concept of workspace, local vault, remote vault, and how they mingle in Dendron.

![dendron-workspace](https://ik.imagekit.io/casa/h7b-dendron/2022-02-02_dendron.remote-full_elP09EX8B.png?ik-sdk-version=javascript-1.4.3&updatedAt=1643846444601){max-width: 300px, display: block, margin: 0 auto}
Credit: [seadude | Dendron community discord](https://discord.com/channels/717965437182410783/783027389919658025/938534904415789096)

2022-02-11, in this [[discussion|notes.tutorial.dendron.discussion-20220211]], Kevin explained the reason why the current url of note in Dendron is not human-readable, which helps the url would not break when user refactor the hierarchy of their notes. He also suggested 2 possible solutions and pointed out how they affect the published site' SEO