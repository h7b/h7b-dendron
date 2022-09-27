---
id: 14joro9x32wakhkdh8skmbo
title: SWITCH
desc: ''
updated: 1653345980185
created: 1653345477769
---
# SWITCH

## Google Sheets

- [Docs](https://support.google.com/docs/answer/7013690?hl=en)
- Usage: Tests an expression against a list of cases and returns the corresponding value of the first matching case, with an optional default value if nothing else is met.
- Syntax
    - `SWITCH(expression, case1, value1, [case2, value2, ...], [default])`
        - `expression` - Any valid values
        - `case1` - The first case to be checked against `expression`
        - `value1` - The corresponding value to be returned if `case1` matches `expression`
        - `case2`, `value2`, … - Optional: Additional cases and values if the first one doesn’t match the `expression`
        - `default` - Optional: An optional value, specified as the last parameter, to be returned if none of the cases match the expression

## Microsoft Excel

- [Docs](https://support.microsoft.com/en-us/office/switch-function-47ab33c0-28ce-4530-8a45-d532ec4aa25e)
- Usage: evaluates one value (called the expression) against a list of values, and returns the result corresponding to the first matching value. If there is no match, an optional default value may be returned.
- Syntax
    - `SWITCH(Value to switch, Value to match1...[2-126], Value to return if there's a match1...[2-126], Value to return if there's no match)`
        - you can evaluate up to 126 matching values and results

## My thoughts

Equivalent to multiple IF conditions, IFS function.

Figure credited to [Sheetgo](https://blog.sheetgo.com/google-sheets-formulas/switch-formula-google-sheets/)
![switch-flow-chart](https://blog.sheetgo.com/wp-content/uploads/2020/12/Switch-image-1.png){max-width: 300px, display: block, margin: 0 auto}

## Related

- [Learn Google Spreadsheets](https://www.youtube.com/watch?v=6N2d0LofLKQ)
    - Learn how to use SWITCH function in Google Sheets or Excel to create multiple If statements. Understand the difference between SWITCH & IFS functions.
    - Function covered in this tutorial: SWITCH, IFS, DGET, YEAR, MONTH
- [Sheetgo](https://blog.sheetgo.com/google-sheets-formulas/switch-formula-google-sheets/)