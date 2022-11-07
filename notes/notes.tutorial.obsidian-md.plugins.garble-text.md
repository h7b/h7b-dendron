---
id: 1pf5dxtq3y1hmeoq1w3a8m9
title: Garble Text
desc: ''
updated: 1667796616192
created: 1654244573210
---
# How to blur text when taking screencap in Obsidian.md app

- GitHub: https://github.com/kurakart/garble-text
- Thoughts:
    - This plugin turns all content in the entire app (notes, sidebar, etc) into unreadable text (and blurs images) so you can take screenshots without exposing sensitive data
    - alternatives: [Privacy Glasses](https://github.com/jillalberts/privacy-glasses)
    - Or I can achieve the same result without using the plugin by
        - While using Obsidian, press `Ctrl + Shift + I` (`Option + Cmd + I` for macOS) to bring up the developer window. Then choose the `Console` tab, and type in
        - `app.garbleText()`: to blur text
        - `app.dom.appContainerEl.removeClass("is-text-garbled");`: to unblur
        - Tutorial screencast: [Obsidian Community](https://www.loom.com/share/20ebce50f6d04b5cbd89cf89643dfb2e)