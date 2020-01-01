---
layout: post
id: 
title : Mac OS X Developer Setup 
description: Description of base setup of Mac OS X for productive development 
tags: osx development dev-environment setup tutorial
category: web
redirect_from:
  - /post/mac-os-x-setup/
---

There are lot of customizations and setup one can and has to do on a fresh Mac OS X installaton. I have been through this several times and this is the distillation of the very basic itemization and workflow to get a base layer to work upon. Some people might work on front-end development, others on more system-side or backend-servers. This provides a foundation upon which you can customize the environment on top of this. I personally work on projects using C++ and Rust.

## Steps ( In Order )

* Install ( or use a fresh install ) Mac OS X. This was written as performed on 10.15.2
* The first thing you want to install is [Xcode][1]. [See these instructions][2] if you want to avoid installing via AppStore for more reliability and a bit more speed.
* [Install Xcode Commandline Tools][3] using ```xcode-select --install``` on the terminal
* [Install `Homebrew`](https://github.com/Homebrew/brew/blob/master/docs/Installation.md). See [5] if you use an account with non-admin privileges for general use.
* Verify installation and environment using ```brew doctor```
* Install Git
    * Option 1 : use Git which comes with Xcode in /usr/bin
    * Option 2 : install latest Git
      * brew install git
      * echo "/usr/local/bin:$PATH" >> ~/.zshrc ( i.e ensure /usr/local/bin precedes /usr/bin in PATH search order )
      ```shell
        ➜ which git
        /usr/local/bin/git
        ➜ git --version
        git version 2.24.1
      ```
* Install Iterm2
  * Font : [Fira Code][7]
  * Color Scheme : [Solarized][8]
* Install [Zsh][9]
  * ```brew install zsh```
  * ```echo "/usr/local/bin/zsh" >> /etc/shells```
  * ```echo "/usr/local/bin:$PATH" >> ~/.zshrc``` ( i.e ensure `/usr/local/bin` precedes `/usr/bin` in `PATH` search order )
  ```shell
    ➜ which zsh
    /usr/local/bin/zsh
    ➜ zsh --version
    zsh 5.7.1 (x86_64-apple-darwin19.0.0)
  ```
  * Configure .zshrc. See a good setup [walkthrough][5]
* Install [Firefox](https://www.mozilla.org/en-US/firefox/new/) & [Microsoft Edge](https://www.microsoftedgeinsider.com/en-us/download)
* Install [Microsoft Visual Studio Code](https://code.visualstudio.com/docs/setup/mac)
    * Vim KeyBindings [^4] : ```code --install-extension vscodevim.vim```
    * Font : [Fira Code][7]
    * Color Scheme : [Solarized][8]
* Optional : Add user to sudoers via admin account
* Optional : Install openssl
* Useful Tools
  * aria2c ( install via Homebrew )
  * diskutil
  * nettop
  * fs_usage
  * top
  * iostat
  * vmstat

[1]: <https://wilsonmar.github.io/xcode/> "Xcode Installation"
[2]: <https://blog.kulman.sk/faster-way-to-download-and-install-xcode/> "Faster Xcode Download"
[3]: <https://stackoverflow.com/questions/9329243/how-to-install-xcode-command-line-tools> "Xcode Commandline Tools"
[4]: <https://discourse.brew.sh/t/homebrew-without-admin-account/524> "Homebrew without admin account"
[5]: <https://www.viget.com/articles/zsh-config-productivity-plugins-for-mac-oss-default-shell/> "Configure Zsh Options & Plugins"
[6]: <https://www.barbarianmeetscoding.com/blog/2019/02/08/boost-your-coding-fu-with-vscode-and-vim> "Visual Studio Code and Vim"
[7]: <https://github.com/tonsky/FiraCode/wiki/Installing> "Fira Code"
[8]: <https://ethanschoonover.com/solarized/> "Solarized Color Scheme"
[9]: <http://zsh.sourceforge.net/> "Z Shell"
[10]: <https://medium.com/@timmykko/using-openssl-library-with-macos-sierra-7807cfd47892> "Openssl on Mac Os X"


