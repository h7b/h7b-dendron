---
id: gjiUUh-JR3_2C4D0O2vPa
title: HTML Open Link New Tab
desc: ''
updated: 1652741099758
created: 1625526336326
---
# HTML tag to Open Link New Tab

Ref: [freeCodeCamp tutorial](https://www.freecodecamp.org/news/how-to-use-html-to-open-link-in-new-tab/)

It's easy to use HTML to open a link in a new tab. You just need an anchor `(<a>)` element with three important attributes:

- The `href` attribute set to the URL of the page you want to link to
- The `target` attribute set `to _blank`, which tells the browser to open the link in a new tab/window, depending on the browser's settings
- The `rel` attribute set to `noreferrer noopener` to prevent possible malicious attacks from the pages you link to

Example:
```html
<a href="https://my.causal.app/models/47260" target="_blank" rel="noopener noreferrer"></a>
```
