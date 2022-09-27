---
id: KinXpNhlg6vHDHZegaato
title: Terminal Emulator
desc: ''
updated: 1643759409424
created: 1643675271743
---
# Terminal emulator

## Customize your terminal in PowerShell or WSL with Oh My Posh
ref: [Microsoft](https://docs.microsoft.com/en-gb/windows/terminal/tutorials/custom-prompt-setup)

This tutorial provides some resources and direction to help you customize your command prompt for PowerShell or Windows Subsystem for Linux (WSL) using [Oh My Posh](https://ohmyposh.dev/). Oh My Posh provides theme capabilities for a fully customized command prompt experience providing Git status color-coding and prompts.

![example](https://docs.microsoft.com/en-gb/windows/terminal/images/custom-prompt.png){max-width: 300px, display: block, margin: 0 auto}

### Getting started

1. install [Homebrew](https://docs.brew.sh/Homebrew-on-Linux#install) to recommended directory `/home/linuxbrew/.linuxbrew`
  ```shell
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```
  Run these two commands in your terminal to add Homebrew to your PATH
  ```shell
  echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/chris/.profile
  eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
  ```
  We recommend that you install GCC
  ```shell
  brew install gcc
  ```
2. Install [Nerd fonts](https://www.nerdfonts.com/font-downloads)  
  I chose [RobotoMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/RobotoMono.zip), since it has dashed zero, curved and straight character lines.
3. Follow the [Linux install guide in the Oh My Posh docs](https://ohmyposh.dev/docs/linux) 
  ```shell
  brew tap jandedobbeleer/oh-my-posh
  brew install oh-my-posh
  ```
  Choose and apply a WSL prompt theme  
    - The Oh My Posh themes will be found in the oh-my-posh directory as JSON files. 
    - Go to `cd $(brew --prefix oh-my-posh)`, then just `cd themes` and `ls` for the list.
    - Copy the theme `agnoster` to my user's `$HOME` folder
    ```shell
    cp agnoster.omp.json $HOME
    ```
  Add the following to ~/.profile
  ```shell
  eval "$(oh-my-posh --init --shell bash --config ~/agnoster.omp.json)"
  ```
  Once added, reload your profile for the changes to take effect.
  ```shell
  . ~/.profile
  ```

DONE

## [Alacritty](https://github.com/alacritty/alacritty) terminal emulator

I followed this [tutorial](https://technixleo.com/install-and-configure-alacritty-terminal-on-windows/) to configure the [custom color schemes](https://github.com/ceciliamay/obsidianmd-theme-primary/issues/87#issuecomment-1086536489), forked from [Obsidian Primary theme](https://github.com/ceciliamay/obsidianmd-theme-primary).