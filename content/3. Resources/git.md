---
id: git
aliases: 
tags:
  - Linux
  - MacOS
  - "#Windows"
publish: true
title: Git Configuration Guide
---
These are just my basic git configurations.
### Install Git

You probably already have Git installed. You can easily check with the following command in your terminal of choice.

```bash
git --version
```

If you find that you don't have git, here is a guide on installing git on your platform of choice.
[Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/)

### Set Git Credentials

Run the following commands in your terminal of choice.

```bash
git config --global user.name "Your Name"
git config --global user.email "Youremail@domain.com"
```

Ideally you would want to verify these with a GPG Key for added security but its generally not required.

### Set Your Default Branch Name 

This one is optional but I like to set my default branch name to ''dominant" because I think its funny and I can.

```bash
git config --global init.defaultBranch dominant
```
