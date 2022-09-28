---
id: e3ke26chd7l4sapctrqgikp
title: Re-initialize a Dendron vault
desc: 'Initialize a new Dendron vault'
updated: 1664325433125
created: 1664323245714
---
# Experience on 2022-09-28

On 2022-09-28, I decide to move the dendron vault out of obsidian vault since the huge quantity of files (20k) in dendron's folder degraded the start-up loading time of obsidian on iOS.

## Setup Git to sync Dendron vault

Steps that I applied:
- create a new blank repo on GitHub (url: git@github.com:h7b/h7b-dendron.git)
- use `GitHub Desktop` to clone the repo into local folder `C:\Users\my-user\my_workspace\h7b-dendron`
- OR open `Git Bash` on Windows then type in
```bash
echo "# h7b-dendron" >> README.md
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:h7b/h7b-dendron.git
git push -u origin main
```
- add ssh keys and passphrase by opening `Git Bash` on Windows (this is the method that works for me). There are some other approaches that I used but don't succeed.
    - I tried to add an environment variable `GIT_SSH` pointed to `/windows/system32/openssh/ssh.exe`
    - I tried in terminal `Start-Service ssh-agent` then `Set-Service ssh-agent -StartupType Automatic` then `ssh-add C:\Users\my_user\ssh\id_ed25519`
    - with `ssh-add -l` I found that there is only 1 key registered and this only key is added into my GitHub account
    - I tried this [guide from GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases) which add a snippet into `C:\Users\my_user\.profile`
- copy `dendron-publish-site.sh` and `netlify.toml` from old vault to new vault
- modify these elements in `dendron.yml`
```yaml
enableSelfContainedVaults: true
preview:
    enableFMTitle: false
workspace:
    vaults:
        -
            fsPath: .
            selfContained: true
            name: h7b-dendron
            sync: sync
    workspaceVaultSyncMode: sync
publishing:
    siteUrl: https://kool.casa/
    seo:
        title: Kool Casa
        description: h7b blog and notes
    logoPath: notes/assets/logo.png
    siteFaviconPath: notes/assets/favicon.ico
    enableFMTitle: false

```
- after having compared with the old vault with the new published vault, I delete the former.