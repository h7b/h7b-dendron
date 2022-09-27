---
id: yjtj8i2qkyewexkg9j2kgd3
title: Date in Metadata
desc: ''
updated: 1662225712189
created: 1662224824634
---
# Date in Metadata

- GitHub: https://github.com/salmund/obsidian-date-in-metadata
- Thoughts:
    - this plugin inserts the current date and time in YAML frontmatter on file creation event. It will automatically insert the date and time on file creation, regardless of the trigger, from a link, a keyboard shortcut, or whatever
    - If you create a new note based on a template using the [[notes.tutorial.obsidian-md.plugins.templater]] plugin which happens to include a YAML frontmatter, the plugin will also update the frontmatter automatically
    - How does it differ from using templates?
        - Using templates to insert date and time is a solution when you want to create a new file with a keyboard shortcut, but when you create a new file from a markdown link, it doesn't work. But this plugin can.
- Demo ![date-in-metadata](https://user-images.githubusercontent.com/105465034/168185897-17e87af8-9d33-4fc9-8164-04de5e1a8883.gif){max-width: 300px, display: block, margin: 0 auto}