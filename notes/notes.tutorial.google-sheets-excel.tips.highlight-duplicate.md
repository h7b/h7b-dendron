---
id: r9zn4p357xeo3gyw3z9gxd8
title: Highlight Duplicate
desc: ''
updated: 1653348717407
created: 1653348077007
---
# Highlight duplicate including partial text matching in Google Sheets

ref: [Stack Overflow](https://stackoverflow.com/questions/57427921/highlight-duplicate-including-partial-text-matching-in-google-sheets)

## Situation:

- I need to highlight values from Column A of Sheet 1 when there is a match in Column A of Sheet 2
- my requirement is also to show partial match in Sheet 1, e.g. if Sheet 1 has another row with "bikram sahu", it also should be highlighted

![question](https://i.stack.imgur.com/dU07b.png){max-width: 300px, display: block, margin: 0 auto}

## Solution:

```java
=REGEXMATCH(LOWER(A1), LOWER(TEXTJOIN("|", 1, INDIRECT("Sheet2!A1:A"))))
```

![solution](https://i.stack.imgur.com/n2eO5.png){max-width: 300px, display: block, margin: 0 auto}