---
layout: page
title: JavaScript IDE - NeoVim
description: JavaScript IDE - NeoVim
keywords: JavaScript IDE, NeoVim
permalink: /env/neovim/
---

# JavaScript IDE - NeoVim

https://neovim.io/

<br/>

## NeoVim installation Ubuntu 20.02

<br/>

**[Snowfoundry Media] Command Line: Neovim Installation and Configuration [ENG, 2020]**  
https://www.youtube.com/watch?v=ZEFXeRIFvN0

<br/>

### Step 1. Setup

    $ mkidr ~/apps && cd ~/apps
    $ curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage

    $ sudo mkdir /opt/nvim

    $ mv nvim.appimage nvim
    $ chmod u+x nvim

    $ sudo mv nvim /opt/nvim

<br/>

    $ sudo vi /etc/profile.d/nvim.sh

<br/>

```
#### NVIM #######################

export NVIM_HOME=/opt/nvim
export PATH=${NVIM_HOME}/:$PATH

alias vi='nvim'
alias vim='nvim'
export EDITOR='nvim'

#### NVIM #######################
```

<br/>

    $ sudo chmod +x /etc/profile.d/nvim.sh
    $ source /etc/profile.d/nvim.sh

<br/>

    $ vi --version
    NVIM v0.4.4

<br/>

### Step 2. Config

<br/>

    // configs file for nvim
    $ mkdir -p ~/.config/nvim/
    $ vi ~/.config/nvim/init.vim

<br/>

```
set number
```

<br/>

### Vim Plugins

https://github.com/junegunn/vim-plug

    $ cd ~/.config/nvim/
    $ mkdir autoload && cd autoload
    $ curl https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim -o plug.vim

<br/>

    $ mkdir -p ~/.config/nvim/plugged
    $ vi ~/.config/nvim/init.vim

```
set number

call plug#begin('~/.config/nvim/plugged')

call plug#end()
```

<br/>

### Step 3. Prepared configs for dev

**[Ben Awad] How to Configure Vim like VSCode [ENG, 2019]**  
https://www.youtube.com/watch?v=gnupOrSEikQ

<br/>

**init.vim:**

    $ vi ~/.config/nvim/init.vim

https://gist.github.com/benawad/b768f5a5bbd92c8baabd363b7e79786f

```
:PlugInstall
```

<br/>

**coc-settings.json:**

    $ vi ~/.config/nvim/coc-settings.json

https://gist.github.com/benawad/e187dd887f256a6a002905ec7f22ad76

<br/>

### 'ryanoasis/vim-devicons'

https://github.com/ryanoasis/vim-devicons

<br/>

### Fonts for plugin 'ryanoasis/vim-devicons'

    $ cd ~/tmp
    $ git clone --depth 1 https://github.com/ryanoasis/nerd-fonts
    $ cd nerd-fonts
    $ ./install.sh

<br/>

### Some issues on start

    $ npm install -g neovim
    $ npm install -g eslint

<br/>

    $ sudo apt install -y python3-pip
    $ pip3 install neovim
