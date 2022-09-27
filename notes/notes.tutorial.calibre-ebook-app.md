---
id: dW3xXZGuTWu5dgS0gM5Tx
title: Calibre Ebook App
desc: ''
updated: 1642631777245
created: 1631323327735
---
# How to Email Books and Documents to Kindle?

Ref: [link](https://www.epubor.com/how-to-email-books-and-documents-to-kindle.html)

Notice that the file size must be under 50MB

- find my Kindle personal email address within Kindle iOS apps or Kindle devices
- add my personal email address to "Send to Kindle" Approved Email list
- configure sender's email login credentials (my personal email address) in Calibre to send documents from Calibre to Kindle
    - email server part in Calibre:
        - hostname: smtp.gmail.com
        - port: 465
        - username: my sender's email login
        - password: my sender's email App Passwords setup for sending from Calibre
            - this step is done as required by guide from Calibre at [link](https://manual.calibre-ebook.com/faq.html#i-cannot-send-emails-using-calibre)
            - read more about App Passwords at this [link](https://support.google.com/accounts/answer/185833) from Google

## Managing subgroups of books by nested tags

ref: [link](https://manual.calibre-ebook.com/sub_groups.html)

- In metadata of book, setup tag hierarchy, separated by `.` (`period`)
    - eg. with `History.Military` tag, the subgroup `Military` is listed under the group `History`
- Go to `Preferences` → `Look & feel` → `Tag browser` and enter the lookup name `tags` into the `Categories with hierarchical items` box. Press `Apply`, and you are done with setting up. 

## Change the default viewer for Calibre to SumatraPDF for epub files

For Windows OS
- Set the default program for opening `epub` files to `sumatrapdf`
- Go to Calibre Preference
- Under Interface, select Behavior
- On the right, is a list of book formats. These are the filetype that the `Calibre Default viewer` will open when you click on a title in the Library browser. Disable whichever format that you don't want Calibre to automatically launch its internal viewer. 
- Click Apply and exit. 

The next time you click on a book, with filetype `epub` or `pdf`, the Windows default reader app, configured by you, will launch instead of the Calibre book viewer.