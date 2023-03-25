---
layout: page
title: NeoVim [Oleksandr Kocherhin] Neovim configs
description: NeoVim [Oleksandr Kocherhin] Neovim configs
keywords: env, ide, neovim, installation, plugins, kocherghin
permalink: /env/ide/neovim/koncherghin/
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
