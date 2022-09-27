---
id: vdiqSQXd_rCr7H-c441_Z
title: VS Code tips
desc: ''
updated: 1659905547054
created: 1625532619492
---
# VS Code tips

## Keyboard shortcuts

![[notes.tutorial.dendron.keyboard-shortcuts#frequently-used-keyboard-shortcuts-for-dendron,1]]

## Bracket pair highlighting

ref: [Visual Studio Code October 2021 (version 1.62)](https://code.visualstudio.com/updates/v1_62#_improved-bracket-pair-guides), [Dendron blog](https://blog.dendron.so/notes/V2Cjla9vzM69Z280j5bXB/)

Settings of interest:
- `editor.guides.bracketPairs: active`: Only show guides for only the active bracket pair.
- `editor.guides.bracketPairs: true`: Show guides for all bracket pairs, with different colors.

## Useful plugins

[Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
- Better Comments extension, as the name suggests, helps you write more human friendly and readable comments
- This extension lets you categorize your comments into alerts, queries, TODOs, highlights, etc. Better Comments also supports a broad range of programming languages
![better-comments-plugin](https://cdn.hashnode.com/res/hashnode/image/upload/v1642344120099/acooXs-06.png?auto=compress,format&format=webp){max-width: 300px, display: block, margin: 0 auto}

[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- helps autocomplete filenames. When you start typing the name of the file in the statements, this plugin will automatically search file names and give you suggestions
![path-intellisense-plugin](https://i.giphy.com/iaHeUiDeTUZuo.gif){max-width: 300px, display: block, margin: 0 auto}

[Tabnine](https://marketplace.visualstudio.com/items?itemName=TabNine.tabnine-vscode)
- This is a code completion assistant powered by Artificial Intelligence which helps you increase your coding accuracy and productivity
![tabnine-plugin](https://github.com/codota/TabNine/raw/master/with-and-without-tabnine-java.gif){max-width: 300px, display: block, margin: 0 auto}

[Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
- This extension enables its users to share a session and collaboratively edit or debug the code. `Live Share` also offers integrated text chat and audio (via plugin [Live Share Audio](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-audio)). All this is possible without the need to configure the same development environment, tools, or settings .
- The Live Share extension is really helpful for activities such as remote code reviews, pair programming and interactive lectures.
![live-share-plugin](https://cdn.hashnode.com/res/hashnode/image/upload/v1642338590890/capHlynjh.png?auto=compress,format&format=webp){max-width: 300px, display: block, margin: 0 auto}

[Peacock](https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock)
- change the color of your Visual Studio Code workspace. Ideal when you have multiple VS Code instances, use VS Live Share, or use VS Code's Remote features, and you want to quickly identify your editor
![peacock-plugin](https://raw.githubusercontent.com/johnpapa/vscode-peacock/main/resources/hero.png){max-width: 300px, display: block, margin: 0 auto}

## Remove blank lines from a text file

ref: [Computer Hope](https://www.computerhope.com/issues/ch000924.htm)

- `Ctrl+H` to open `Replace` modal
- In the Replace window, in the `Find what`, type `^\n` and leave the `Replace` with blank
    - caret (`^`), which is a regular expression and a way of saying the beginning of the line
    - the `\n` escape sequence, which is a newline
    - or  the `\r`, which is a carriage return
- Tick the Regular Expression option

## Take Multiple Cursors at Start/End of Each Line in VS Code

ref: [shouts.dev](https://shouts.dev/articles/take-multiple-cursors-at-start-end-of-each-line-in-vs-code#:~:text=Open%20the%20desired%20file%20and,the%20end%20of%20every%20line.)

Open the file and select all desired lines. Then press `SHIFT + ALT + I` to insert multiple cursors at the end of each line. So, all cursors are at the end, then we can add the same text at the end of every line.