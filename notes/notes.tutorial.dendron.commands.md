---
id: rCwsMYbdz2WZASEvVse1U
title: Commands
desc: ''
updated: 1640862458287
created: 1632870521662
---
# Frequently used commands

## When I need to refactor notes
ref: [Dendron wiki](https://wiki.dendron.so/notes/0fFWWockAV3L7mMMJOyGF/), [Dendron discord](https://discord.com/channels/717965437182410783/735365126227493004/919354849668251688)

- `Dendron: Rename Note`: Renames a single note
- `Dendron: Move Note`: Moves a single note to a different vault, can rename during move
- `Dendron: Refactor Hierarchy`: When you wish to rename a collection of notes at one time by changing pieces of the hierarchy

Some slight differences, but they also all include updating backlinks referencing the note. Refactoring is the most powerful one, and is able to do the most at one time.

## Sync all notes with git
ref: [Dendron wiki](https://wiki.dendron.so/notes/c4cf5519-f7c2-4a23-b93b-1c9a02880f6b/#workspace-sync)

`Workspace: Sync`: any changes you made will be pushed back to remote, and any changes in the remote will be pulled

## Refactor hierarchy multiple notes in Dendron

I want to move all children node of some node to another node.

Currently at v0.74 Dendron does not have dedicated command to do this. But I can use the regex capabilities of `Dendron: Refactor Hierarchy`
- For example, in my case: 
    - Use command `Dendron: Refactor Hierarchy`
    - Match text: `(note\.A)\.(.*)`
        - Explain: match all notes under the `note.A.` hierarchy by using two `catching group ()` in regex
    - Replace text: `note.B.$2`
        - Explain: The 2nd catching group `(.*)` is accessible in the `Replace text` prompt as `$2`
    - Behavior: will move all children while leaving `note A` available alone.
    ![refactor-example](https://i.imgur.com/Koh2JkY.jpg){max-width: 300px, display: block, margin: 0 auto}

According to Dendron [discord](https://discord.com/channels/717965437182410783/925907625311359036/925917145077010443), they have plan to wrap the regex needed for common refactoring operations into a convenient command.