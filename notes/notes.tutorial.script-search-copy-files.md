---
id: Pw7yTOYQHdrW6wez
title: Script Search Copy Files
desc: ''
updated: 1642118666316
created: 1626218661316
---
# Use Python to automate boring task 'Search and Copy files'

## Situation: 
I have many files whose filenames are stored in a column in an Excel file. I want to search these files, which were stored locally in my computer, and then copy them to a designated folder. I’m using MacOS X (version 10.11.6).

The structure of the Excel file is as follow.
![structure-excel-file](https://i.imgur.com/troM71w.png){max-width: 300px, display: block, margin: 0 auto}


## Solution:

Use `Applescript` (via `Automator`) or `Python`.

### My choice: Use `Python`  
Idea: write a python script that read input from a `listFile.csv`, search for all filenames in that csv file from a designated folder path, then copy all found files to a folder. Run the script by excecuting in terminal
```bash
> python3 searchCopy.py
```

Clone this [gist](https://gist.github.com/h7b/70646c21acf1bc9e83c405ef14cbf1f9) in a folder and practice.

### Other possibilities: Use `AppleScript`
ref: [discussion in Apple Communities](https://discussions.apple.com/thread/5528059?tstart=0)

In order to use AppleScript, I need to locate `Applescript Editor` in `/Applications/Utilities` (or search for it in `Spotlight`). Then I copy the script into Automator (as indicated in the screencap below)

![screencap01](https://i.imgur.com/YFb4Ft4.png){max-width: 300px, display: block, margin: 0 auto}

Thoughts: I tried but did not successfully with these AppleScript, just listed here for references.

#### Method 1:
Search entire directory including subfolders
> Note: the Excel file must be opened while script being executed

Clone this [searchCopy1.scpt](https://gist.github.com/h7b/70646c21acf1bc9e83c405ef14cbf1f9#file-searchcopy1-scpt) to test.

#### Method 2:
Search entire directory,subfolders included, for an exact match. Then output an error if the file does not exist (in a file named “error.txt” on the Desktop)

> Note: the Excel file must be opened while script being executed

Clone this [searchCopy2.scpt](https://gist.github.com/h7b/70646c21acf1bc9e83c405ef14cbf1f9#file-searchcopy2-scpt) to test.

#### Method 3:
To avoid scripting the various spreadsheet apps, an idea comes up where the user selects the cells in spreadsheet apps, copies to clipboard, and then the script processes the data copied to clipboard instead of relying on data in spreadsheet apps.

Clone this [searchCopy3.scpt](https://gist.github.com/h7b/70646c21acf1bc9e83c405ef14cbf1f9#file-searchcopy3-scpt) to test.