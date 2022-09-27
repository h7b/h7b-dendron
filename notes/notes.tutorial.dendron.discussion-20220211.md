---
id: Lsm95lGehMUBfI0JCRiOA
title: Discussion 20220211
desc: ''
updated: 1644591561051
created: 1644591347393
---
# Thread discussing the readability of a url in Dendron

ref: [Thread](https://discord.com/channels/717965437182410783/941427880024502333), [message](https://discord.com/channels/717965437182410783/941427880024502333/941527416763973672)

User friendly urls are possible, the reason we haven't implemented it is because the urls would break whenever you refactor. 
say you have the following:
- note: cooking.pasta
- url: /notes/cooking-pasta

If you refactor your note to cooking.vegan-pasta, then your url would now break. 

Our plan to address readability as well as making sure links don't break after refactoring is by appending the id after the human readable portion of the link:

- note: cooking.pasta
- url: /notes/cooking-pasta-uthxkcpgcdmvdqdd2iy7n

In the above example, uthxkcpgcdmvdqdd2iy7n is the uid of the note. When dendron gets a request, the cooking-pasta is ignored, we just look at the id at the end which means you can refactor and still have a sensible link. 

The caveat for the above implementation is that for it to work properly (aka for google to index the site), it requires a server component (you would need to use netlify to host - github pages won't be able to support this). 

So a few options for human readable urls:

1. we can support regular human readable urls today (/notes/cooking-pasta). the issue is that the link would break on refactor
2. we can support human readable urls with an id /notes/cooking-pasta-uthxkcpgcdmvdqdd2iy7n and use client side javascript to figure out the right url. your links won't break but it means your site won't be indexed by search engines because they can't index on client side redirects
2. we can support human readable urls with an id /notes/cooking-pasta-uthxkcpgcdmvdqdd2iy7n and use server side redirects. this would make it incompatible with github pages and you'd need to use a hosting provider with server side support (which netlify and vercel support)