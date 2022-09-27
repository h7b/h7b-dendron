---
id: xgkohg66bcrqsgrb36wekrk
title: Data Sheet
desc: ''
updated: 1656287738617
created: 1656286001671
---
# Data Sheet

This [spreadsheet](https://docs.google.com/spreadsheets/d/1OOEPLCrdq5ODI9fu4yrQKV_rqEypfsvpfNRs1FKYozU/edit?usp=sharing) contains the collected price data point.

## Note on spreadsheet

### Sheet "data"

Cell A1
- purpose: create the ordered column number
- formula: 
    ```javascript
    =ArrayFormula(SEQUENCE(1,MATCH(2,1/(A2:2<>""))))
    ```

Column "markup vs apple-us (vnd)"
- purpose:
    - calculate markup price with respect to "apple-us":
    $1-\frac{Price_{otherSeller}}{Price_{appleus}}$
- formula:
    ```javascript
    =($G3-QUERY(
                {data!$B$3:$B,data!$C$3:$C,data!$D$3:$D,data!$E$3:$E,data!$F$3:$F,data!$G$3:$G},
                "SELECT Col6 WHERE Col1 contains '"&$B$3&"' AND Col2 contains '"&$C$3&"' AND Col3 contains '"&$D$3&"' AND Col4 contains '"&$E$3&"' AND Col5 contains '"&$F$3&"'"
               )
    )/QUERY(
        {data!$B$3:$B,data!$C$3:$C,data!$D$3:$D,data!$E$3:$E,data!$F$3:$F,data!$G$3:$G},
        "SELECT Col6 WHERE Col1 contains '"&$B$3&"' AND Col2 contains '"&$C$3&"' AND Col3 contains '"&$D$3&"' AND Col4 contains '"&$E$3&"' AND Col5 contains '"&$F$3&"'"
        )
    ```

Column "helper_col_0"
- purpose: 
    - helper column to apply conditional formatting based on group of data
    - join the text from other columns, remove all non-printable characters, remove spaces
- formula:
    ```javascript
    =ARRAYFORMULA(TRIM(CLEAN(SUBSTITUTE(B3:B&C3:C&D3:D&E3:E," ",""))))
    ```

Column "helper_col_1"
- purpose:
    - helper column to apply conditional formatting based on group of data
    - if the text in Column "helper_col_0" are identical, the record belongs to the same group.
- formula:
    ```javascript
    =MATCH($N3,UNIQUE($N$3:$N),0)
    ```

Conditional format rules
- custom formula:
    ```javascript
    =ISEVEN($helper_col_1)
    ```
- purpose:
    - apply color to group that has even numerical order in Column "helper_col_1"
    - using the `$` sign to lock the column reference to column "helper_col_1"

## Related resources

- [How To Apply Conditional Formatting Across An Entire Row In Google Sheets](https://www.benlcollins.com/spreadsheets/conditional-formatting-entire-row/)
- [Conditional Format Based on Group of Data in Google sheets](https://infoinspired.com/google-docs/spreadsheet/conditional-format-based-on-group-of-data-in-google-sheets/)