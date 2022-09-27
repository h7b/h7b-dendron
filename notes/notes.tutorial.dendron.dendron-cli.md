---
id: uN2WNYUHoWGRK1evOO9Vo
title: Dendron CLI
desc: ''
updated: 1640063900175
created: 1637765564126
---
# Dendron Command Line Interface (CLI)

ref: [Dendron wiki](https://wiki.dendron.so/notes/23a1b942-99af-45c8-8116-4f4bb7dccd21/)

Installation  
```bash
npm install -g @dendronhq/dendron-cli
```
Upgrade  
```bash
npm install -g @dendronhq/dendron-cli@latest
```
Show version number
```bash
dendron doctor --version
```

## Dendron Publish CLI

ref: [Dendron wiki](https://wiki.dendron.so/notes/yQVhJtdQ40n3SLHJKAeeU/#export)

**Question:** 

I'm using Dendron v0.69.1, vscodium v1.62.3

The execution duration of command `Dendron: Publish Export` now is quite long. 40 min for my vault with 144 notes. The longest process is Installing dependencies, which takes at least 35 min

I feel unease to answer these 4 questions at separated stages, whenever I run the command `Dendron: Publish Export`

- default behavior or config?
- skip build process?
- select export target? Github/
- docs folder already exists. Remove and continue?

Is there anyway to config to set the default options for all of these 4 questions or at least choose the answer at the beginning instead of during running phase?

**Answer:** from Dendron team in [discord](https://discord.com/channels/717965437182410783/911269551134609499/912007341824675931)

there isn't from the plugin. if you submit a feature request, we can prioritize it. meanwhile, you have to use the [CLI](https://wiki.dendron.so/notes/yQVhJtdQ40n3SLHJKAeeU.html#export) to automate the publishing

In Dendron v0.69.1, in order to reduce friction when running command `Dendron: Publish Export` from command palette, execute this terminal command within my workspace
> dendron publish export --target github --yes

**My update on 20211123:** today I move my repo folder to the SSD from the old place HDD. And try to publish using CLI, the duration reduces drastically to only 2min. Impressive!  
