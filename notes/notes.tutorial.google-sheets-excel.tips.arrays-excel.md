---
id: jd8bsoo0sanqju1xnw9z20b
title: Array formulas in Excel
desc: Use array formulas in Excel
updated: 1662303265211
created: 1662302906371
---
# Excel Functions: Using Array formulas

ref: [meadinkent](http://www.meadinkent.co.uk/xlarrays.htm)

Many functions such as SUM or MAX can incorporate selection criteria rules and may be combined with the IF function using arrays. This means that the sum or average function will be performed on only those items that meet a criteria.

Example:
- `{=SUM(IF(G6:G12=$H$14, F6:F12, 0))}` means: Sum values in F6:F12 where the operator initials in G6:G12 are equal to H14

This is an Array formula and this is evidenced by the curly brackets {braces}.

When you enter an array formula there are three rules you must follow:
- Instead of typing `<Enter>` to place the function in a cell, you must type `<Ctrl> + <Shift> + <Enter>`
- You can not type the braces `{}`. They are entered automatically with the above key combination. If you don't do so, the formula probably won't make sense and will cause an error
- The array ranges (for the criteria and the values) must be the same size