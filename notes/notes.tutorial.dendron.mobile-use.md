---
id: n5Fr9vDFUxyDSxF6l4oEr
title: Edit Dendron vault on iOS
desc: ''
updated: 1664274573070
created: 1642180076564
---
# My current workflow to edit Dendron vault on iOS

So after having used the [[Netlify publishing workflow|notes.tutorial.dendron.publish-netlify]] to remove the heavy build data from the Dendron vault folder.

I want to go further by separating the `.git` folder out of the files I want tracked

So I came up with 2 possible solutions:
1. I separate the location of `.git` subfolder out of the folder `./blog-dendron-repo/` that I want to track and sync via iCloud Drive.  
    ref: [Stack Overflow](https://stackoverflow.com/questions/505467/can-i-store-the-git-folder-outside-the-files-i-want-tracked), [jdhao's blog](https://jdhao.github.io/2020/12/25/git_directory_work-tree_explained/), [LogicBig](https://www.logicbig.com/tutorials/misc/git/custom-git-dir.html)
2. Or I keep the location of `.git` subfolder inside the folder `./blog-dendron-repo/` but exclude the `.git` subfolder from `iCloud Drive` sync.  
    ref: [Apple Communities](https://discussions.apple.com/thread/251290283)

I incline to the 1st option, since there is no possible way to make the 2nd choice to work without breaking the Git workflow.

## Getting started

1. On Windows, go to the `Obsidian` folder in `iCloud Drive` 
    ```shell
    C:\Users\huytr\iCloudDrive\iCloud~md~obsidian>
    ``` 
2. Clone my remote repo `h7b-dendron-netlify` into this `Obsidian` folder,
    ```shell
    git clone --separate-git-dir=C:/Users/huytr/my_workspace/h7b-dendron-git/.git https://github.com/h7b/h7b-dendron-netlify
    ```
    The result of this command:  
    the *git-directory* folder, located at `C:/Users/huytr/my_workspace/h7b-dendron-git/.git`,   
    is separated from the *work-tree* current location `C:/Users/huytr/iCloudDrive/iCloud~md~obsidian/h7b-dendron-netlify`
3. Open Obsidian on iOS, import the new vault `h7b-dendron-netlify`
    - Install plugin `Breadcrumbs`
    - In `Breadcrumbs` settings > 
        - `Alternative Hierarchies` > `Dendron Notes` > enable `Add Dendron notes to graph`, enable `Trim Dendron Note Names`. This is mandatory to navigate the hierarchy structure of Dendron notes within Obsidian
        - `Views` > `Trail/Grid` > `Views to show`: enable the 1st option only. This is optional for my preferences only
    - In `Options` > `About` > `Advanced` > `Override config folder`: type in `.obsidian.ios`. This is optional to separate the settings I used for Obsidian iOS
4. Append `.obsidian` and `.obsidian.ios` into `.gitignore` file in `h7b-dendron-netlify` folder.

DONE.

Now my workflow will be:
- Edit Dendron notes on the fly on mobile using Obsidian iOS
- Changes will sync to my laptop via iCloud Drive
- When i'm on desk with laptop, I open VSCodium and commit changes to the remote GitHub repo
- The static site will then be built and deployed automatically by Netlify

## Thoughts

Update 2022-09-27: since the size of the dendron-based vault becomes quite large (1k files with temporary files from nodejs), Obsidian on iOS needs 5s to startup and loading files, which makes me feel unusable. So I moved the Dendron out of Obsidian vault on iOS.