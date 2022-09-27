---
id: 9vvcgt62c82ixgwl96xn9n4
title: Remove Duplicates in String
desc: ''
updated: 1653349328606
created: 1653348576807
---
# Remove duplicates in a string - google sheets

ref: [Stack Overflow](https://stackoverflow.com/questions/59934220/duplicates-in-string-google-sheets)

## Situation:

I have a cell, (coming from an extracted DB) in Google sheets looking like this: `MOMO EL COCO LISTO EL SAFWAN MOMO EL COCO LISTO EL SAFWAN (Mister)`

I want to get the non-duplicate entry which should be: `MOMO EL COCO LISTO EL SAFWAN`

## Solution:

```java
=TEXTJOIN(" ", 1, UNIQUE(TRANSPOSE(SPLIT(REGEXEXTRACT(A1, "(.+)\("), " "))))
```

![solution](https://i.stack.imgur.com/mi48D.png){max-width: 300px, display: block, margin: 0 auto}