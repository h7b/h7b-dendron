---
id: dft1156nwrunrsma9dmyegh
title: clean-embeds
desc: Change the appearance of embedded blocks
updated: 1659908022484
created: 1659906432186
---
# Change the appearance of embedded blocks

## Situation

Sometimes you want to construct a larger "master document" from its parts, say chapters. And it should look like it's been made of one piece. So you want to make the transclusion to be blended in seamlessly.

Assuming a sample markdown note:

```markdown
---
cssclass: clean-embeds
---

# Test Embeds

- Enable `clean-embeds` under *Settings → Appearance → CSS snippets*.
- Use `cssclass: clean-embeds` in YAML frontmatter to enable "clean" embedding.

![[Test Quote]]
![[Blindtext - Lorem Ipsum]]

## Document continued here
```

With "normal" embeds, it would look like this:
![normal-embed](https://forum.obsidian.md/uploads/default/optimized/2X/b/bfdb0bcf41e25b1897f0ad9181f239193d9b661c_2_771x750.png){max-width: 300px, display: block, margin: 0 auto}

Using the custom `cssclass: clean-embeds`, it looks like this:
![css-embed](https://forum.obsidian.md/uploads/default/optimized/2X/0/06e16bc10b778aa552cc381039cdf8c1c7ed7874_2_771x750.png){max-width: 300px, display: block, margin: 0 auto}

## Version A: apply clean-embeds to only specific notes

ref: [Obsidian forum](https://forum.obsidian.md/t/meta-post-common-css-hacks/1978/394)

Install

1. Copy the [CSS code](https://gist.github.com/h7b/49274e60432696067c4e707257768047) and save it into your vault's `.obsidian/snippets` folder under the name `clean-embeds.css`
2. Restart Obsidian
3. Enable `clean-embeds` under `Settings → Appearance → CSS snippets`
4. Add this to your YAML frontmatter for notes that should use clean embeds: `cssclass: clean-embeds`

## Version B: apply clean-embeds to all notes

ref: [Obsidian forum](https://forum.obsidian.md/t/meta-post-common-css-hacks/1978/411)

Install

1. Copy the [CSS code](https://gist.github.com/h7b/18cd8f7bc8543501438318c7105896ec) and save it into your vault's `.obsidian/snippets` folder under the name `clean-embeds-all.css`
2. Restart Obsidian
3. Enable `clean-embeds-all` under `Settings → Appearance → CSS snippets`