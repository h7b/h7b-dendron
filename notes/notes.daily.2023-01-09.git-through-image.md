---
id: gaqwgijacg3326nh5cbeb0w
title: Git through images
desc: 'Understanding Git through images'
updated: 1673232974678
created: 1673229469754
tags: cat.tut
---
# Understanding Git through images

ref: [bytebytego](https://blog.bytebytego.com/p/ep-40-git-workflow), [nopenoshishi](https://dev.to/nopenoshishi/understanding-git-through-images-4an1)

Git is a distributed version control system. Every developer maintains a local copy of the main repository and edits and commits to the local copy. The commit is very fast because the operation doesn’t interact with the remote repository. If the remote repository crashes, the files can be recovered from the local repositories.
![git-bytebytego](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd47de46b-2c7b-43d2-8a9a-a2ebb7600347_1324x2004.jpeg){max-width: 300px, display: block, margin: 0 auto}

A repository in Git is a storage for files, which can be remote or local.
- Remote repository is a repository where the source code is placed on a server on the Internet and can be shared by everyone.
- Local repository is a repository where the source code is located on your computer and only you can make changes.

`Clone`: Duplicate a copy of the remote repository into your development environment (local repository and working directory).
![clone](https://res.cloudinary.com/practicaldev/image/fetch/s--euEralRx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rml9wqair7kg7wsisi9u.png){max-width: 300px, display: block, margin: 0 auto}

A working directory is not any special directory, but a directory where you always work on your computer. You can think of it as a directory where you can connect to the target directory that Git manages (in this case, project) with a Git staging area or local repository.
![working-directory](https://res.cloudinary.com/practicaldev/image/fetch/s--AQRpB2lo--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/foxzc5v3gd5d11umzzj8.png){max-width: 300px, display: block, margin: 0 auto}

Changes to the source code are made through the working directory, the staging area. Actually, in the working directory, we work.
![changes](https://res.cloudinary.com/practicaldev/image/fetch/s--5cSI9xvv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rjld228v47s0o3c0zyjc.png){max-width: 300px, display: block, margin: 0 auto}

`Add`: move the modified file to the staging area. It is a feature of Git that there is a cushion before changes are reflected in the local repository. Add files from the working directory to the staging area and prepare them for commit.
![add](https://res.cloudinary.com/practicaldev/image/fetch/s--g-n9rTeT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0rsaucz4mwif9mqgqh4j.png){max-width: 300px, display: block, margin: 0 auto}

`Commit`: register the file in the staging area to the local repository. At this moment, a commit object is created.
![commit](https://res.cloudinary.com/practicaldev/image/fetch/s--zJpzHIFL--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/879r8a67bbpd686bm23s.png){max-width: 300px, display: block, margin: 0 auto}

`Push`: when the work is done, you register the changes from the local repository into the remote repository
![push](https://res.cloudinary.com/practicaldev/image/fetch/s--8GeH4YtV--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/u0ijlyrhm1gwgn44374q.png){max-width: 300px, display: block, margin: 0 auto}

We can see the changing points in the file (or the differences between two versions of the file) with `diff`

`Staging area`:
- As development work grows, we often make many changes in one working directory
- What happens if you put all the changes in a local repository at once? In this case, when parsing the commits, you may not know where a feature was implemented
- In Git, it is recommended to do one `commit` per feature
- This is why there is a `staging area` where you can divide the commit unit into smaller units.
![staging-area](https://res.cloudinary.com/practicaldev/image/fetch/s--JIqnMvxx--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5i00yr7n7bv01fi217zl.png){max-width: 300px, display: block, margin: 0 auto}

The concept of Git is to `stage` only what is needed, and then proceed with the work or `commit` ahead of time to promote efficient development that can be traced back through the history of each implementation.

The basic workflow is to `clone` once, then `add`, `commit`, and `push` for each working.

We create a `branch` to change and add files in multiple branches
- The files saved in the `main` branch are in ongoing use
- The reason for the separate branches is to work without affecting the currently running source code.
- create a branch: `git branch <new branch>`
- create a branch and moves you to that branch: `git checkout -b <new branch>`

Moving the branch is called `checking out`.
- The pointer to the branch you are currently working on is called `HEAD`
- moving from the `main` branch to the `develop` branch means changing the `HEAD`
- As in picture, both branches point to the `commit` named `Atr3ul`. You just added `second.txt` by committing `Atr3ul` in the main branch, so you are ahead of the commit `f27baz`.
![checkout](https://res.cloudinary.com/practicaldev/image/fetch/s--Uj1sMlY9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/loxgrl33lwvjz3n39pkp.png){max-width: 300px, display: block, margin: 0 auto}

Let's say you change `second.txt` in the `develop` branch and make a new `commit`
- Then the `develop` branch created a commit called `m9sgle` and pointed to that commit
- The current `HEAD` position (working branch position), what stage the file has been worked on, or the status of who is working on it is called `status`.
![status](https://res.cloudinary.com/practicaldev/image/fetch/s--gAYgyTYM--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qfk2fgoa06mq3pmbd2g8.png){max-width: 300px, display: block, margin: 0 auto}

The arrow on the `commit` represents the relationship between a "parent" commit and a "child" commit. The assumption of `parent←-child` is that how much the child (commit) born from the parent (commit) has grown (changed).

The way of managing branches will vary on each development team. Here are two simple general models to grow branches in Git
- Git-Flow ![git-flow](https://res.cloudinary.com/practicaldev/image/fetch/s--oag6F_6a--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6qa7upoeya40kmmtu1ch.png){max-width: 300px, display: block, margin: 0 auto}
    - `master`: Branch to release a product. No working on this branch
    - `develop`: Branch to develop a product. When ready to release, merge to `release` branch. No working on this branch
    - `feature`: Branch for adding features, merged into `develop` when ready to be released
    - `hotfix`: For urgent post-release work (critical bug fixes, etc.), branch off from `master`, merge into `master`, and merge into `develop`
    - `release`: For preparation of product release. Branch from `develop` with features and bug fixes to be released. When ready for release, merge to `master` and merge to `develop`.
- GitHub-Flow ![github-flow](https://res.cloudinary.com/practicaldev/image/fetch/s--A2q5LwmG--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/39y36qwrpkuaiw0oryw2.png){max-width: 300px, display: block, margin: 0 auto}
    - is a simplified model of the Git-Flow. It consists of only `master` and `feature`
    - The important difference is the cushion of `pull requests`, which allows integration between branches. `Pull request` is to insert a process where a higher level developer reviews the code. ![pull-request](https://res.cloudinary.com/practicaldev/image/fetch/s--5oZBMKVy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yge3as35z6o70kpmfg6f.png){max-width: 300px, display: block, margin: 0 auto}

I am currently working on the `feature` branch and have created the following `third.txt`.
![merge](https://res.cloudinary.com/practicaldev/image/fetch/s--xrwx0T8s--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/aq641yqw80zrlyek0cg6.png){max-width: 300px, display: block, margin: 0 auto}

After some local work, you may be faced with a situation where the remote repository has been updated by another developer. In this case, you can use `pull` to re-install the information from the remote repository back into the local repository.


