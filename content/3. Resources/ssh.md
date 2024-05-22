---
id: ssh
aliases: 
tags:
  - Linux
  - MacOS
  - Windows
  - Resources
publish: true
title: SSH Configuration Guide
---
A quick SSH Guide
### Install SSH Client

You probably have an SSH Client installed, here is how to check.

```bash
ssh -V
```

If you don't have it installed the method varies on operating systems.
#### Linux

Its as simple as using your distributions package manager!

```bash
# Debian/Ubuntu
sudo apt install openssh-client

# Arch Linux/Manjaro
sudo pacman -S openssh

# OpenSUSE:
sudo zypper install openssh

# Fedora
sudo dnf install -y openssh-clients
```

SSH should start automatically, you can check with the following command.
```bash
systemctl status sshd
```

If its not running you can run the following commands.
```bash
# Run command to start 
sudo systemctl start sshd

# Run command to start automatically on boot.
sudo systemctl enable sshd
```
#### MacOS

OpenSSH should be installed but is usually outdated so you can update with the following command.

```zsh
brew install openssh
```

You can check that its running with
```bash
ps -ax | grep ssh-agent
```
To start it, run:
```bash
eval $(ssh-agent)
```
#### Windows

Windows is a little more complicated so the full comprehensive guide is linked below.
[Install OpenSSH on Windows](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=powershell)

### Generate SSH Key Pairs

Now its time to generate your SSH key pair with
```bash
ssh-keygen -t ed25519 -b 4096 -C "username@emaildomain.com" -f ~/.ssh/ssh-key-name
```
> Note: If you are on Windows  the '~' which leads to the home directory only works on Powershell


You will then be prompted for a passphrase, which you will be required to input every time you use this key.

Since I am using this key with GitHub I will name the file github.

You can follow this guide to add your public key to github.
[Add SSH Key to GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

If your ssh client is unable to find your key automatically, you can specify which key to use with the ssh config file in `~/.ssh/config`

If the file is not found you may create it.
```bash
# ~/.ssh/config

Host github
	HostName github.com
	IdentityFile ~/.ssh/github
```
