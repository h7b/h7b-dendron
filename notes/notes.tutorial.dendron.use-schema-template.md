---
id: 0CUUNDwNeRutJrqHZATuk
title: Use Schema Template
desc: ''
updated: 1661118863675
created: 1642443093888
---
# How do I use schema and templates in Dendron
ref: [Dendron wiki | Making Your First Schema](https://wiki.dendron.so/notes/5U4eAiqshI67VxIL40KWH/)

[Templates](https://wiki.dendron.so/notes/861cbdf8-102e-4633-9933-1f3d74df53d2/) are notes with pre-outlined content meant for reuse

[Schema](https://wiki.dendron.so/notes/c5e5adde-5459-409b-b34d-a0d75cbb1052/) is a *YAML* file that helps you to apply consistent structure to all your notes. One of the primary capabilities for schema is to automatically insert templates into new notes

## Situation
When writing new notes in `reading` section, I found that I need to retype many duplicated words. I want to reduce the effort to write these types of note

## Solution

I have to create a schema and template for my notes in `reading` section.
- schema: to organize the structure of notes
- template: to reproduce the outline of content

I follow this [guide](https://wiki.dendron.so/notes/5U4eAiqshI67VxIL40KWH/)
1. Create a `notes-reading` template with the [variables](https://wiki.dendron.so/notes/x4n8mvhvc0nmi9agxtnqp3t/) for current date
    ![[templates.notes-reading]]
    Next, in the frontmatter of `templates.md`, set `nav_exclude: true` to hide this `template` note from the navigation bar
2. Create a `notes` schema via `notes.schema.yml`
    ```yml
    # Schema for my reading notes
    # It wil match 
    #     root.notes.reading
    #     root.notes.reading.note1
    #     root.notes.reading.note2
    # It will not match
    #     root.notes.reading.note1.highlight 
    
    version: 1
    imports: []
    schemas:
      - id: notes
        title: notes
        parent: root
        children:
          - pattern: reading
            namespace: true
            template: templates.notes-reading
    ```

DONE

## Usage
When I want to create new note in `reading` section
1. Open `Dendron: Lookup Note` (`Ctrl+L`)
2. Type in: `notes.reading.new-note-name`

Result: a new note will be created with info from `reading` template.

## Helpful resources:
- [Ryan Randall | some-dendron-starter-files](https://github.com/ryan-p-randall/some-dendron-starter-files)
- [Bassmann | dendron-schemas](https://github.com/Bassmann/Dendron-schemas)
- [dendron-site | dendron.schema.yml](https://github.com/dendronhq/dendron-site/blob/master/vault/dendron.schema.yml)