---
title: Install oh-my-zsh system-wide
description: Guide to install oh-my-zsh for the entire system.
published: true
date: 2022-03-13T21:45:11.950Z
tags:
editor: markdown
dateCreated: 2022-03-13T21:45:11.950Z
---

# Install oh-my-zsh system-wide
In this short guide, I will teach you how to easily install oh-my-zsh for an entire system.

## 1. Requisites
You need to have the dependencies for oh-my-zsh installed in your system. Those are:
- git
- sudo
- zsh
- chsh (optional)

## 2. Install oh-my-zsh as root as usual
You can follow the instructions in [their website](//ohmyz.sh). It's important that you do it as root, not with sudo.

## 3. Copy the installation folder to a location available for all users
I chose to use `/opt/etc`, so my command would be:
```bash
cp -r /root/.oh-my-zsh /opt/etc/oh-my-zsh
```

## 4. Modify the ZSH variable in the .zshrc file of root
Modify the document so it has this line:
```bash
export ZSH="/opt/etc/oh-my-zsh"
```

## 5. Clean up
You can now remove the directory `/root/.oh-my-zsh`

## 6. Optional - Create a template of the .zshrc file for other users
You can get the template of the .zshrc file in `/opt/etc/oh-my-zsh/templates/zshrc.zsh-template`. Copy it to another location (to avoid being overwritten when updating) and modify the lines that sets the location of the oh-my-zsh directory, and disable auto-updates, like so:
```bash
export ZSH="/opt/etc/oh-my-zsh"
zstyle ':omz:update' mode disabled
```
