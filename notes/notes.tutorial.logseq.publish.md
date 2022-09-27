---
id: vhwimc3rv48is56b46x8187
title: Publish
desc: ''
updated: 1660964856949
created: 1660964692423
---
# Publish Logseq notes online

## List of solutions

- Publishing with Logseq app on desktop via `export public pages` feature:
    - tutorial at [here](https://logseq.github.io/#/page/Publishing%20(Desktop%20App%20Only))
    - Pricing: free
    - this feature simply bundles the whole Logseq web app with your public pages and let you deploy them as a static website
    - deploy to anywhere supporting static hosting, like GitHub Pages, Netlify, Vercel
    - [demo page](https://docs.logseq.com/#/page/Contents)
- [Logseq Publish](https://github.com/logseq/publish)
    - a tool that generates a fast, SEO-friendly, and scalable website from your Logseq content
    - output assets code size is smaller than `export public pages` feature on Desktop App
    - Pricing: free
    - deploy to anywhere supporting static hosting, like GitHub Pages, Netlify, Vercel
    - [demo page](https://eloquent-keller-6512b6.netlify.app/)
- [Logseg Publish Action](https://github.com/marketplace/actions/logseq-publish)
    - [document](https://pengx17.github.io/knowledge-garden/#/page/logseq%20publish%20github%20action) written by author, that explains what does this GitHub Action do
    - thoughts: I don't understand, just put here and turn back to investigate later when I have much more interest with Logseq
- [logseq Schrödinger](https://github.com/sawhney17/logseq-schrodinger) community plugin for Logseq
    - a plugin that export Logseq pages to [Hugo](https://gohugo.io/) static site
    - you first build the Hugo website and then drag the contents of the export to the contents folder in Hugo. The plugin doesn't create a website, it formats Logseq pages to the format accepted by Hugo for posts