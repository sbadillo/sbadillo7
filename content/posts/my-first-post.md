---
title: Setting up First Post
date: 2020-04-07

image : "/images/black-cohosh.png"
excerpt: alsdkasd askda ls
draft: false
---
Personal notes on setting up non-essentials

```sh
# 2 ways to check linux distr and version

$ hostnamectl
$ lsb_release -a

# update package index
$ sudo apt-get update

# install git
$ sudo apt-get install git
$ sudo apt-get install vim

# install pydf
$ sudo apt-get install pydf

# Install zsh and its plugin manager Antigen

# install zsh
$ sudo apt-get install zsh
$ chsh -s $(which zsh)
$ echo $SHELL

# use curl to get latest Antigen, and get autojump on the side.
$ curl -L git.io/antigen > antigen.zsh
$ sudo apt-get install autojump

modify ~/.zshrc to use antigen :
```

```file
# ~/.zshr 

source $HOME/antigen.zsh

export TERM="xterm-256color"

# needed to add all programs installed by pip --user to the path.
# export PATH=$PATH:~/.local/bin

# custom commands executed everytime a terminal is opened: 
## make graph of disk usage
# pydf -h -m 

# Load oh-my-zsh library
antigen use oh-my-zsh

# Bundles from the default repo (robbyrussells)
antigen bundle git
antigen bundle autojump
antigen bundle themes
antigen bundle command-not-found
antigen bundle colored-man-pages

# Bundles from other sources:
## Syntax highlighting bundle.
antigen bundle zsh-users/zsh-syntax-highlighting

## Fishlike auto suggestions
antigen bundle zsh-users/zsh-autosuggestions

## Extra zsh completions
antigen bundle zsh-users/zsh-completions

# load the theme
antigen theme robbyrussell

# Tell antigen that you are done
antigen apply
```

Running zsh next time will install those plugins. We are ready to go !