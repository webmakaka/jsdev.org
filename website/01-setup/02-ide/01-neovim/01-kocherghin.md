---
layout: page
title: NeoVim [Oleksandr Kocherhin] Neovim configs
description: NeoVim [Oleksandr Kocherhin] Neovim configs
keywords: env, ide, neovim, installation, plugins, kocherghin
permalink: /setup/ide/neovim/koncherghin/
---

# NeoVim [Oleksandr Kocherhin] Neovim configs

https://www.youtube.com/watch?v=YrLiugDhCuk

<br/>

```
$ cd ~/.config/nvim
$ rm -rf *
$ git clone https://gitlab.com/ejiqpep/nvim-config .
```

<br/>

```
$ cd autoload
$ curl https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim -o plug.vim
```

<br/>

```
$ mkdir -p ~/.config/nvim/plugged
$ nvim ~/.config/nvim/init.vim
```

<br/>

```
:PlugInstall
```

<br/>

### [On Error Message] neovim [coc.nvim] build/inderx.js not found, please install dependencies and compile coc.nvim : yarn install

```
$ cd ~/.config/nvim/plugged/coc.nvim/
$ yarn install
$ yarn build
```

<br/>

### Commands

Switch to file browsing mode

:Ex or if that is not working use :Explore

<br/>

```
d for creating a directory

% for creating a new file
```
