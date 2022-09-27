---
id: 8nlztsk79beeyqejtc6uj60
title: Note Traits
desc: ''
updated: 1659735088711
created: 1659734092786
---
# Use "note traits" to customize note

ref: [Dendron wiki](https://wiki.dendron.so/notes/bdZhT3nF8Yz3WDzKp7hqh/)

Note traits let you customize the data of notes using code.

There are some customization that you can not do with templates alone (such as change the name and title of the note automatically), so Dendron introduce this "note traits" concept.

The trait behaviors are defined by Javascript code that employ the [note traits' API](https://wiki.dendron.so/notes/oOIEFJc6DTgS71mmh89WQ/).

Some examples of trait behavior:
- [Note with Date Hierarchy](https://wiki.dendron.so/notes/kwgbkl58xka0zsib8uhhkfw/)
    - This trait closely mirrors the functionality of Journal Notes, but allows you to put the notes under a different domain
- [Using Hierarchy Position](https://wiki.dendron.so/notes/dws0n0eez2i3ln5as6eur0i/)
    - This trait demonstrates how you can use your current hierarchy position to create a new note
- [Workflow to manage contacts with Dendron](https://github.com/dendronhq/arboretum/blob/main/notes/workflow.managing-contacts.md)
    - This workflow employ a trait to apply a template and note name for each note of contact