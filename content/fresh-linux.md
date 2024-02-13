---
id: fresh-linux
aliases: []
tags:
  - Linux
publish: true
title: Fresh Linux Todo List
---

- Install Git (Might be included)

- Git pull Dotfiles Repo
`$ git clone git@github.com:RestedWicked/.dotfiles.git`

- Install dotfiles

- Set Git Credentials

- Set SSH config

- Install Zsh

- Set Zsh as default login shell
`$ chsh -s %(which zsh)`
or  
`% sudo lchsh %USER`
for fedora

- Install Oh-my-zsh
`$sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

- Install Zsh Plugins
    - zsh-autosuggestions
    `$ git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
    - zsh-syntax-highlighting
    `$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
    - fash-syntax-highlighting
    `$ git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting`

- Install Rust
`$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

- Install Packages
```
// sccache
$ cargo install sccache --locked
// starship
$ cargo install starship --locked
// RipGrep
$ cargo install ripgrep
// Bacon
$ cargo install bacon --locked
// eza
$ cargo install eza
// fd
$ cargo install fd-find
```

- Install Fzf

- Install Tmux

- Install Neovim

