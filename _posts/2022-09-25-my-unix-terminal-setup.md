---
title: My Unix Terminal Setup
description: Alvin's personal terminal setup for Unix terminals
date: 2022-09-25T20:13:00-07:00
categories:
    - blog
tags:
    - unix
---

1. Install `zsh` and dependencies.  
```sh
sudo apt install zsh curl  # for Ubuntu
```
or  
```sh
brew install zsh curl      # for MacOS
```
This is an alternative to the `bash` shell
that comes as default in many operating system. See 
[this article](https://linuxhint.com/differences_between_bash_zsh/#:~:text=It%20has%20many%20features%20like,by%20default%20with%20Linux%20distribution.)
for a comparison between `bash` and `zsh`.

2. Install `Oh My Zsh` (see the [official website](https://ohmyz.sh/)).
```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
`Oh My Zsh` is a customizable framework for easily managing configurations and plugins for `zsh`.

3. Install `zsh-autosuggestions` (see the official [repo](https://github.com/zsh-users/zsh-autosuggestions))  
First clone its repository into `oh my zsh` default plugin directory with the following command.
```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
Then edit `~/.zshrc` (the `zsh` config file similar to `~/.bashrc` for `bash`) and add
`zsh-autosuggestions` to the list of plugins, e.g.
```sh
plugins=(
    # other plugins...
    zsh-autosuggestions
)
```
If you re-launch your terminal, you should see history command hinting by now.

4. Install `powerlevel10k` theme.  
    1. Install the recommended fonts for pretty icons (open the file and click "install")
        - [MesloLGS NF Regular.tff](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
        - [MesloLGS NF Bold.tff](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
        - [MesloLGS NF Italic.tff](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
        - [MesloLGS NF Bold Italic.tff](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

    2. Clone the [repository](https://github.com/romkatv/powerlevel10k#oh-my-zsh) with the following command
    ```sh
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```

    3. set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.  

    4. `source ~/.zshrc` and configure following the prompts.

    `powerlevel10k` has massive performance improvement over the popular `powerlevel9k` theme.

Ta-da, there goes a beautiful and responsive terminal. Leave a comment about how you like / dislike 
about this setup.
