---
id: ile00yfqcmxr58ulfpf7spd
title: IMPORTXML
desc: 'IMPORTXML'
updated: 1672715411598
created: 1670540474957
---
# IMPORTXML

## Google Sheets

- [Docs](https://support.google.com/docs/answer/3093342?hl=en)
- Usage: Imports data from any of various structured data types including XML, HTML, CSV, TSV, and RSS and ATOM XML feeds.
- Syntax
    - `IMPORTXML(url, xpath_query)`
    - `url` - The URL of the page to examine, including protocol (e.g. `http://`)
    - `xpath_query` - The XPath query to run on the structured data
- Notes:
    - `IMPORTXML` function automatically check for updates **every hour** while the **document is open**, even if the formula and sheet don’t change [^1]
    - If you delete and re-add cells or overwrite the cells with the same formula, it triggers a refresh of the function
    - If you open and refresh the document, it won’t trigger a refresh on the function

[^1]: https://support.google.com/docs/answer/12188454?hl=en

## Related

- [n8n | How to import XML to Google Sheets: 3 step-by-step techniques](https://blog.n8n.io/import-xml-google-sheets/)