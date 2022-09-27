---
id: p6DAGnvvh2NUL4A2zsAW6
title: Image in Dendron
desc: Dendron image
updated: 1662247866838
created: 1631926358221
---
# How to customize image in Dendron

## Resize image and display

ref: [Images | Dendron Wiki](https://wiki.dendron.so/notes/a91fd8da-6895-49fe-8164-a17acd8d9a17/)

By appending [CSS properties](https://wiki.dendron.so/notes/a91fd8da-6895-49fe-8164-a17acd8d9a17/#allowed-css-properties), Dendron allow me to 
- limit the width of the image
    - `width` sets a fixed size for it
    - `max-width` will set the maximum size but will allow smaller sizes (for example, on mobile)
    - example: 
    ```code
    ![](/assets/images/example.png){max-width: 300px}
    ```
- centering
    - This image will be smaller, and will be centered in the page.
    - The code for it looks like this:
    ```code
    ![](/assets/images/example.png){max-width: 300px, display: block, margin: 0 auto}
    ```
## Better preview of shared link of Dendron published page 

If you share a Dendron-published link on social media (Discord server, Twitter...), without insterting image tag, the preview will be like this
![link preview without image tag](https://i.imgur.com/7ZBG3G0.png){max-width: 300px, display: block, margin: 0 auto}

By inserting proper image tag in the frontmatter of the particular article, you will get a better preview
![link preview with image tag](https://i.imgur.com/18skuua.png){max-width: 300px, display: block, margin: 0 auto}

The example of the frontmatter with `image` tag is as follows.
```yaml
---
id: fDCVPEo3guCFWPdxokXHU
title: Best Mobile Note-Taking Apps for Markdown
desc: ''
updated: 1635183157051
created: 1632684719327
date: '2021-10-25'
excerpt: An overview of mobile apps that work well with Markdown
author: Derek Ardolf
image:
  url: https://org-dendron-public-assets.s3.amazonaws.com/images/blog-mobile-editor-header.png
  alt: Mobile phone sitting ontop of a journal
publish: true
---
```

## Trick to update embedded image in multiple notes

Instead of just using image links `![img](img.link)` throughout your docs, using note refs with a single image link. 

Trick:
- Create a Dendron note that contains all of the images that need to be referenced, with a dedicated header for each image  
  ```md
  ![Tutorial Welcome Screen](https://org-dendron-public-assets.s3.amazonaws.com/images/tutorial-welcome-screen-2.png)
  ```
  Example notes with all of image links:
[dendron-github-all-images](https://github.com/dendronhq/dendron-site/blob/master/vault/asset.preview.md#tutorial-dendron-layout-dark)
- Then use Dendron note ref throughout docs for specific images
  ```md
  ![[dendron://dendron.dendron-site/asset.preview#tutorial-dendron-layout-dark,1:#*]]
  ```
  Example embedded image in other notes:
[dendron-image-other-note](https://github.com/dendronhq/dendron-site/blob/a9373e4ae16c1dd00eca79d9328336c5f54277d3/vault/dendron.tutorial.user-interface.md?plain=1#L14)

Benefits:
- allows me to change / update image in one place, and it will be updated everywhere it was referenced within my vault
- have a note with an image with a caption, and metadata

Current limitation of this trick (wrt Dendron v0.74):
- cannot do image formatting with inline css as presented in previous section
- I can insert note refs into a Markdown table, though it may not render or look the way you may want if having more customization options available

There is a discussion about this issue in [Dendron GitHub](https://github.com/dendronhq/dendron/issues/1450)

## Embed video in a note
ref: [Dendron GitHub Issue 533](https://github.com/dendronhq/dendron/issues/533), [markdown-it-html5-embed](https://github.com/cmrd-senya/markdown-it-html5-embed)

Dendron has not supported rich content link yet.

So I can not use
```markdown
![test-video](https://example.com/file.webm)
```

But I have to use html tag
```html
<p><video width="320" height="240" class="audioplayer" controls>
<source type="video/webm" src="https://example.com/file.webm"></source>
Your browser does not support playing HTML5 video. You can
<a href="https://example.com/file.webm" download>download a copy of the video
file</a> instead.
</video></p>
```