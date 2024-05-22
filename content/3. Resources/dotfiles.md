---
id: dotfiles
aliases: 
tags:
  - Linux
  - "#MacOS"
  - Resources
publish: true
title: Dotfiles Install Guide
---

These are my current dotfile configurations that I use for my work with Linux, and sometimes windows. If you would like to just use my Neovim config, here is a guide for that.

## Git Configuration

Assuming you are starting from a brand new system you will need to configure git for this guide.

[[git|Git Configuration Guide]]
## SSH Configuration

I prefer to use SSH to handle my git transactions, its more secure since I use 2FA, and I don't want to keep inputting my password every time.

[[ssh|SSH Configuration Guide]]

## Dotfiles Configuration

We can now install the dotfiles. Right now this is Linux and MacOS specific, until I setup a proper windows support.
### Requirements (Linux & MacOS)

You will need the following before installing.
#### GNU Stow
Check with:
```bash
stow -v
```
If not then install with your package manager.
#### Zsh
You can find instructions [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH).

If not then install with your package manager. Don't change your default shell yet.
If you have a .zshrc file already, move or remove it for now.
#### Rust
You probably don't have this installed but its easy as running this command:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Then install the following crates:
```bash
cargo install sccache --locked
cargo install starship --locked
cargo install ripgrep
cargo install eza
cargo install zoxide
cargo install fd-find
cargo install bat
cargo install bacon --locked
```
> Note: You may also use `cargo binstall` to download compiled binaries you can find more info [here](https://github.com/cargo-bins/cargo-binstall)

#### FZF
You can find it [here](https://github.com/junegunn/fzf?tab=readme-ov-file#installation).
#### TMUX
You can find it [here](https://github.com/tmux/tmux/wiki/Installing).

Also run this command to install the plugin manager:
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

After you install the dotfiles, run tmux and press `prefix + I`
In my case `prefix` is bound to `C-b`
#### Neovim
You can find it [here](https://github.com/neovim/neovim/blob/master/INSTALL.md#install-from-package).

#### A NerdFont
You can use any font [here](https://www.nerdfonts.com/font-downloads).
I use ProFont

### Install Dotfiles

Now that you have installed the pre-requisites, you may run the following command to put the dotfiles repo in `~/.dotfiles`
```bash
git clone --recurse-submodules git@github.com:RestedWicked/.dotfiles.git ~/.dotfiles
```

CD into it and run:
```bash
./server.sh
```

This script will automatically symlink all the folders into their correct positions.
If you have folders in those positions the symlink will fail, you will have to move or remove those folders first, and then retry the command.

Now you can set Zsh as your default shell.
```bash
chsh -s $(which zsh) 

# if you use fedora run this instead
sudo lchsh $USER
```

### Install Oh-my-zsh
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install Plugins

# Autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Syntax Highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Fast Syntax Highlighting
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting

```

If installing oh-my-zsh replaces the `.zshrc` you can just move the `.zshrc.pre-oh-my-zsh` back to `.zshrc`

## Extras
These are optional.
### Install Node Version Manager

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

### Install Node
```bash
nvm install 18.14.0
```
