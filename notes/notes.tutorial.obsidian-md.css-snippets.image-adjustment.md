---
id: f3bc02ckh0443y63yupvjqx
title: image-adjustment
desc: move position and resize the images in the notes within an Obsidian vault
updated: 1659952689198
created: 1659950968925
---
# Image Adjustments

ref: [Obsidian Hub](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/CSS+Snippets/Image+Adjustments)

## Situation

I want to move/position and resize the images in my notes within my Obsidian vault.

## Install

1. Copy the [CSS code](https://gist.github.com/h7b/b16d10557d064d89f22f17ef35a6b411) and save it into your vault's `.obsidian/snippets` folder under the name `image-adjustment.css`
2. Restart Obsidian
3. Enable `image-adjustment` under `Settings → Appearance → CSS snippets`

## Usage

ref: [Obsidian--ITS-Theme](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/Guide/Image-Positions.md)

### Syntax

```markdown
![[Internal Image.png|attribute attribute2]]
![[Internal Image.png|sban cover hs-med]]

![External Image|attribute attribute2](image.png)
![External Image|sban cover hs-med](image.png)
```

### Attributes

- [positioning](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/Guide/Image-Positions.md#leftrightcenter)
    - `left/right/center`: move the image to the left/right/center
    ![img-position](https://github.com/SlRvb/Obsidian--ITS-Theme/raw/main/Images/Image_Adjustments-Simple-Positions.png){max-width: 300px, display: block, margin: 0 auto}
- [sizing](https://github.com/SlRvb/Obsidian--ITS-Theme/blob/main/Guide/Image-Positions.md#sizing)
    - `hs-med`: 300px in height
    - `ws-med`: 300px in width
    ![img-size](https://github.com/SlRvb/Obsidian--ITS-Theme/raw/main/Images/Image_Adjustments-Custom-Sizing.png){max-width: 300px, display: block, margin: 0 auto}