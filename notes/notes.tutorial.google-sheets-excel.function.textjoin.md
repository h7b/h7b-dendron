---
id: ggv80z8copyo6u9nbm8l4r2
title: TEXTJOIN
desc: ''
updated: 1653342631195
created: 1653342532483
---
# TEXTJOIN

## Google Sheets

- [Docs](https://support.google.com/docs/answer/7013992?hl=en)
- Usage: Combines the text from multiple strings and/or arrays, with a specifiable delimiter separating the different texts.
- Syntax
    - `TEXTJOIN(delimiter, ignore_empty, text1, [text2, ...])`
        - `delimiter` - A string, possibly empty, or a reference to a valid string. If empty, text will be simply concatenated
        - `ignore_empty` - A boolean; if `TRUE`, empty cells selected in the text arguments won't be included in the result
        - `text1` - Any text item. This could be a string, or an array of strings in a range
        - `text2`, ... [OPTIONAL] - Additional text item(s).