---
layout: post
id: 9b558909-dc3e-4c6f-a2a8-26da88aa4830 
title : Mac OS X Developer Setup 
description: Description of base setup of Mac OS X for productive development 
tags: osx mac development dev-environment setup tutorial
category: [development]
redirect_from:
  - /post/mac-os-x-setup/
version: 0.2
---

When I get a new Mac or do a fresh install of OS X, I used to be faced with enormous decision on the minimal basic things I need to configure and install. There are lot of customizations and setup one can and has to do on a fresh Mac OS X installaton. Usually this led me to painful hours of reseach of various people's setup. Over time, after numerous times of doing this, I distilled and narrowed down to the following base layer upon which I can plan to install other customizations. 

Some people might work on front-end development, others on more system-side or backend-servers. I personally work on projects using C++ and Rust. The following gives you a solid ***common*** ground with utmost necessary things to start upon and gives you unabmiguous and working instructions. It is not biased or specialized for any specific environments.

## Steps ( In Order )

* Install ( or use a fresh install ) Mac OS X. This was written as performed on 10.15.2 and configure System Preferences as needed

* The first thing you want to install is [Xcode][1]. See these [instructions][2] if you want to avoid downloading via Appstore for more reliability and a bit more speed.

* Install [Xcode Commandline Tools][3] using ```xcode-select --install``` on the terminal

* Install [Homebrew][homebrew]
  * git clone from Homebrew repo or use provided script
  * See [instructions][4] if you use an account with non-admin privileges for general use

* Verify installation and environment so far using ```brew doctor```. This usually confirms all required tools and permissions for previous steps. All following tools can be installed using [Homebrew][homebrew] from this point onward

* Install Git
    * Option 1 : use Git which comes with Xcode in /usr/bin
      ```shell
        ➜ /usr/bin/git --version
        git version 2.21.0 (Apple Git-122.2)
      ```
    * Option 2 : install latest Git
      * brew install git
      * echo "/usr/local/bin:$PATH" >> ~/.zshrc ( i.e ensure /usr/local/bin precedes /usr/bin in PATH search order )
      ```shell
        ➜ which git
        /usr/local/bin/git
        ➜ git --version
        git version 2.24.1
      ```

* Install [Iterm2][iterm2]
  * ```brew install iterm```
  * Font : [Fira Code][7], Color Scheme : [Solarized][8]

* Install [Zsh][zsh]
  * Mac Os X >= Catalina comes with Zsh, but you need to upgrade to latest Zsh yourself.
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

* Install Browsers
  * [Firefox][firefox] 
  * [Microsoft Edge][edge] ( chrome based - it is really good !! )

* Install [Microsoft Visual Studio Code][vscode]
    * [Vim KeyBindings][6] : ```code --install-extension vscodevim.vim```
    * Font : [Fira Code][7], Color Scheme : [Solarized][8]

* Optional
  * Add user to sudoers via admin account, if needed
  * Install [Openssl][openssl]

* Some useful tools to keep in mind for general use 
  * [aria2][aria2] ( install via Homebrew )
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
[zsh]: <http://zsh.sourceforge.net/> "Z Shell"
[openssl]: <https://medium.com/@timmykko/using-openssl-library-with-macos-sierra-7807cfd47892> "Openssl on Mac Os X"
[firefox]: <https://www.mozilla.org/en-US/firefox/new/>
[vscode]: <https://code.visualstudio.com/docs/setup/mac> "Microsoft Visual Studio Code For Mac"
[homebrew]: <https://github.com/Homebrew/brew/blob/master/docs/Installation.md> "Homebrew"
[edge]: <https://www.microsoftedgeinsider.com/en-us/download> "Microsoft Edge"
[iterm2]: <https://iterm2.com/> "Iterm2"
[aria2]: <https://aria2.github.io/> "Aria2"