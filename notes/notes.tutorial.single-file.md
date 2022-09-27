---
id: lvop6aj73efiezj8xpbg1mi
title: SingleFile
desc: ''
updated: 1663363057885
created: 1646700066577
---
# SingleFile: Save a complete web page into a single HTML file
ref: [Hacker News](https://news.ycombinator.com/item?id=30527999)

GitHub repo: 
- [SingleFile](https://github.com/gildas-lormeau/SingleFile): 
  - a Web Extension (and a CLI tool) compatible with Chrome, Firefox (Desktop and Mobile), Microsoft Edge, Vivaldi, Brave, Waterfox, Yandex browser, and Opera. It helps you to save a complete web page into a single HTML file
  - The HTLM file then can be opened in any web browser
  - Images are stored as [data URIs](https://en.wikipedia.org/wiki/Data_URI_scheme)
  - SingleFile also includes an annotation editor to remove ads and/or other unwanted html visual elements while keeping the style, without installing any additional extension. Further, the editor also allows to save the page as it appears in the reader mode [^1]
- [SingleFileZ](https://github.com/gildas-lormeau/SingleFileZ): 
  - a fork of SingleFile that allows you to save a webpage as a self-extracting HTML file. This HTML file is also a valid ZIP file which contains the resources (images, fonts, stylesheets and frames) of the saved page
  - The HTML file then can be opened in any web browser which has installed SingleFileZ extension with the activated option "Allow access to file URLs"
  - Images are stored as entries in a zip file

[^1]: SingleFile uses the Firefox implementation for the reader mode, see [Readability.js](https://github.com/mozilla/readability)

Demo video:
<p><video width="320" height="240" class="audioplayer" controls>
<source type="video/mp4" src="https://user-images.githubusercontent.com/396787/156664907-cc458e35-f41b-45ca-91eb-372213812b44.mp4"></source>
Your browser does not support playing HTML5 video. You can
<a href="https://user-images.githubusercontent.com/396787/156664907-cc458e35-f41b-45ca-91eb-372213812b44.mp4" download>download a copy of the video
file</a> instead.
</video></p>

## My personal config for SingleFile plugin

- File name
    - template
        - my modified value: `{date-iso} - {page-title}[50ch] ({time-locale}).html`
        - default value: `{page-title} ({date-locale} {time-locale}).html`

## Related

- Alternative: [Save Page WE](https://chrome.google.com/webstore/detail/save-page-we/dhhpefjklgkmgeafimnjhojgjamoafof)