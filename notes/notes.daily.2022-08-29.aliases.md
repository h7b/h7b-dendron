---
id: 1z1e0u9tvw41rk6nhdngeyz
title: Aliases in Obsidian and Logseq
desc: Aliases in Obsidian and Logseq
updated: 1662249245485
created: 1662248471854
tags: cat.read
---
# Use of aliases in various note taking apps

ref: [goedel](https://www.goedel.io/p/the-importance-of-aliases)

## Why aliases?

Aliases are different names for the same piece of information.

For example the German word “Philosophie”, the English word “Philosophy” and the Italian word “Filosofia” all mean the same. If you are working with content in different languages (or even make notes in different languages), you most probably want to collect all notes around the topic “Philosophy” in one place - regardless of the language, in which they are written.

Another reason for using aliases is abbreviations. If a doctor is using the word “ARVC”, he is most probably talking about “Arrhythmogenic right ventricular cardiomyopathy”. I’m pretty sure that you would want all information regarding this disorder of the myocardium, which is the muscular wall of the heart in one place.

The third reason is different grammatical forms, plural, and singular, subject and object.

Last but not least our language is full of subtle variations of names called synonyms. Examples are software/program, house/mansion/building, and buy/purchase.

## How Logseq handles Aliases

[[notes.tutorial.logseq]] supports the definition of aliases using a syntax "alias:: Filosofia, Philosophie".

Once you have defined your aliases, you can work with them as if they were independent pages.

![logseq](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc8bc4656-d696-46ac-a4ae-3992211e9031_1358x566.png){max-width: 300px, display: block, margin: 0 auto}

How Logseq has implemented Aliases? 
- Each time you create an alias, a virtual new page will be created with the alias name as the page title. You can see them in the all-pages list, you can click on them and therefore you can use them as if they were real pages. 
- Linking to an alias just creates a normal markdown wiki link to the alias page. Logseq takes care of linking it to the original keyword page in the background.
- But other applications may not know about Logseq using Aliases at all.

![logseq-implement](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa93d38f2-4912-427d-9d33-76396b110f76_2366x1164.png){max-width: 300px, display: block, margin: 0 auto}

## How Obsidian handles Aliases

[[notes.tutorial.obsidian-md]] supports defining Aliases in the note's frontmatter with syntax "aliases: Filosofia, Philosophie".

![obsidian](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F618e2b1b-8ce1-4c16-a30b-4268ff720512_2228x604.png){max-width: 300px, display: block, margin: 0 auto}
