---
id: jxNAqo4sHHlMT1tuzg0QJ
title: Dropdown List Autocomplete
desc: ''
updated: 1639108344917
created: 1639002153645
---
# Create an autocomplete dropdown list in Google Sheets

ref: [Learn Google Spreadsheets](https://www.youtube.com/watch?v=B3TmdmZfdDM)

Situation: I want to create a dropdown list with data validation which automatically save new choice from input

Idea: create a secondary helper table named `Option` which is a copy of the main list by putting the range of main list into an `array`. Then use this `Option` table as `Criteria` for `Data validation` of main list.
