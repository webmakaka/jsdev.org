---
layout: page
title: JavaScript IDE - NeoVim - Installation in Ubunu 20
description: JavaScript IDE - NeoVim - Installation in Ubunu 20
keywords: env, ide, neovim, installation, plugins
permalink: /env/ide/neovim/
---

# JavaScript IDE - NeoVim

<br/>

**Official website:**  
https://neovim.io/

<br/>

**Plugins:**  
vimawesome.com

<br/>

## NeoVim installation in Ubuntu 20

<br/>

### Step 0. Install Packages

<br/>

**Install NodeJS**

**<a href="/env/nodejs/">Nodejs should be installed</a>**

<br/>

**Install Golang (some plugins need golang) (Optional)**  
https://golang.org/doc/install

<br/>

```
$ mkdir ~/tmp
$ cd ~/tmp/
$ wget --no-check-certificate https://golang.org/dl/go1.18.3.linux-amd64.tar.gz
```

<br/>

```
$ tar -xvzpf go1.18.3.linux-amd64.tar.gz
$ sudo mkdir -p /opt/go.1.18
$ sudo mv go/* /opt/go.1.18/
$ sudo ln -s /opt/go.1.18/ /opt/go
```

<br/>

```
$ sudo vi /etc/profile.d/golang.sh
```

<br/>

```
#### GO 1.18 ########################

export GO_HOME=/opt/go
export PATH=${GO_HOME}/bin:$PATH

#### GO 1.18 ########################
```

<br/>

```
$ sudo chmod +x /etc/profile.d/golang.sh
$ source /etc/profile.d/golang.sh
```

<br/>

```
$ go version
go version go1.18.3 linux/amd64
```

<br/>

### Step 1. Setup

```
$ mkdir ~/apps && cd ~/apps
$ curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage

$ sudo mkdir /opt/nvim

$ mv nvim.appimage nvim
$ chmod u+x nvim

$ sudo mv nvim /opt/nvim
```

<br/>

```
$ sudo vi /etc/profile.d/nvim.sh
```

<br/>

```
#### NeoVIM #######################

export NVIM_HOME=/opt/nvim
export PATH=${NVIM_HOME}/:$PATH

alias vi='nvim'
alias vim='nvim'
export EDITOR='nvim'

#### NeoVIM #######################
```

<br/>

```
$ sudo chmod +x /etc/profile.d/nvim.sh
$ source /etc/profile.d/nvim.sh
```

<br/>

```
// I also decided to add aliases in the bottom of file
$ sudo vi /etc/bash.bashrc
```

<br/>

```
alias vi='nvim'
alias vim='nvim'
```

<br/>

```
$ vi --version
NVIM v0.8.1
```

<br/>

### Install Additional fonts and icons

**ryanoasis/vim-devicons**

https://github.com/ryanoasis/vim-devicons

<br/>

```
$ cd ~/tmp
$ git clone --depth 1 https://github.com/ryanoasis/nerd-fonts
$ cd nerd-fonts
$ ./install.sh
```

<br/>

### Install package manager for neovim (Vim Plugins)

https://github.com/junegunn/vim-plug

<br/>

```
$ curl -fLo ~/.config/nvim/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

<br/>

```
$ mkdir -p ~/.config/nvim/plugged
$ vi ~/.config/nvim/init.vim
```

<!--

:CocList

call CocAction('runCommand', 'tsserver.organizeImports')

-->

<!--

command! -nargs=0 OR :call CocAction('runCommand', 'editor.action.organizeImport')

-->

<br/>

```js
set encoding=utf-8
set noswapfile
set number
set scrolloff=8
set colorcolumn=79
set list
set listchars=tab:→\ ,space:·,nbsp:␣,trail:•,eol:¶,precedes:«,extends:»
set wildignore+=*/tmp/*,*/dist/*,*/node_modules/*,*.so,*.swp,*.zip,package-lock.json

" show existing tab with 2 spaces width
set tabstop=2
" when indenting with '>', use 2 spaces width
set shiftwidth=2
" On pressing tab, insert 2 spaces
set expandtab

call plug#begin('~/.config/nvim/plugged')

" Stable version of coc
Plug 'neoclide/coc.nvim', {'branch': 'release'}

" Keeping up to date with master
Plug 'neoclide/coc.nvim', {'do': 'yarn install --frozen-lockfile'}


Plug 'scrooloose/nerdtree'
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'tiagofumo/vim-nerdtree-syntax-highlight'

Plug 'ctrlpvim/ctrlp.vim'
Plug 'ryanoasis/vim-devicons'

" Automatic close parens
Plug 'jiangmiao/auto-pairs'

" Colorscheme
Plug 'morhetz/gruvbox'
Plug 'crusoexia/vim-monokai'

" Emmet
Plug 'mattn/emmet-vim'

" highlight colors
Plug 'rrethy/vim-hexokinase', { 'do': 'make hexokinase' }

" css3 syntax highlight
Plug 'hail2u/vim-css3-syntax'

" Syntax hightlight for .js
Plug 'pangloss/vim-javascript'

" Syntax highlight for .ts
Plug 'HerringtonDarkholme/yats.vim', { 'for': 'typescript' }

" Syntax highlight for .tsx
Plug 'ianks/vim-tsx', { 'for': 'typescript.tsx' }

" Syntax hightlight for Vue.js
Plug 'posva/vim-vue'

"Plug 'iamcco/coc-angular', {'branch': 'release'}
Plug 'airblade/vim-gitgutter'

" Syntax hightlight for .jsx
Plug 'mxw/vim-jsx'

"Commenting
Plug 'preservim/nerdcommenter'

"Airline
Plug 'vim-airline/vim-airline'

"Tailwindcss
Plug 'iamcco/coc-tailwindcss',  {'do': 'yarn install --frozen-lockfile && yarn run build'}

"Grahql
Plug 'jparise/vim-graphql'

call plug#end()

syntax on
colorscheme gruvbox

filetype plugin indent on

let g:NERDTreeWinPos = "right"
let g:NERDTreeIgnore = ['^node_modules$']

let g:ctrlp_use_caching = 0
let g:ctrlp_working_path_mode = 0
let g:ctrlp_custom_ignore = '\v[\/]\.(git)$'
let g:ctrlp_custom_ignore = 'node_modules\|dist\'

" coc config
let g:coc_global_extensions = [
  \ 'coc-snippets',
  \ 'coc-pairs',
  \ 'coc-tsserver',
  \ 'coc-eslint',
  \ 'coc-prettier',
  \ 'coc-json',
  \ 'coc-html',
  \ 'coc-css',
  \ 'coc-vetur',
  \ ]

"mappings
map <C-n> :NERDTreeToggle<CR>

"block Ctrl + Z
nnoremap <c-z> <nop>

"block arrows
noremap <Up> <Nop>
noremap <Down> <Nop>
noremap <Left> <Nop>
noremap <Right> <Nop>

"block mouse coursor
set mouse=

"Insert a newline without entering in insert mode, vim
nmap oo o<Esc>k
nmap OO O<Esc>j

"CTRL + S to save
nmap <c-s> :w<CR>
vmap <c-s> <Esc><c-s>gv
imap <c-s> <Esc><c-s>

"CTRL + Z to undo
nnoremap <c-z> :u<CR>      " Avoid using this**
inoremap <c-z> <c-o>:u<CR>

nmap <F2> :update<CR>
vmap <F2> <Esc><F2>gv
imap <F2> <c-o><F2>

noremap <F3> :set invnumber<CR>
inoremap <F3> <C-O>:set invnumber<CR>

nmap <silent> gd <Plug>(coc-definition)

inoremap jk <esc>

" Use `:ORGANIZE` for organize import of current buffer
command! -nargs=0 ORGANIZE :call CocAction('runCommand', 'tsserver.organizeImports')

" Use `:Prettier` command for coc
command! -nargs=0 Prettier :CocCommand prettier.formatFile

" Use `:Format` to format current buffer
command! -nargs=0 Format :call CocAction('format')

" Pre Save
autocmd BufWritePre *.js :ORGANIZE
autocmd BufWritePre *.ts :ORGANIZE
```

<br/>

```
:PlugInstall
```

<br/>

**Emmet cheat sheet**  
https://docs.emmet.io/cheat-sheet/

<br/>

**Commenter settings:**  
https://vimawesome.com/plugin/the-nerd-commenter

<br/>

**Tailwind:**  
https://github.com/iamcco/coc-tailwindcss

<!--

```
:source ~/.config/nvim/init.vim
:PlugInstall
```
-->

<br/>

### coc-settings.json:

**configuration-options**  
https://github.com/neoclide/coc-tsserver#configuration-options

<br/>

    $ vi ~/.config/nvim/coc-settings.json

```json
{
  "javascript.preferences.importModuleSpecifier": "non-relative",
  "javascript.preferences.quoteStyle": "single",
  "typescript.preferences.importModuleSpecifier": "non-relative",
  "typescript.preferences.quoteStyle": "single",
  "suggest.noselect": false,
  "coc.preferences.formatOnSaveFiletypes": [
    "javascript",
    "typescript",
    "typescriptreact",
    "javascriptreact",
    "typescript.tsx",
    "graphql",
    "vue",
    "css",
    "html",
    "json"
  ],
  "eslint.autoFixOnSave": true
}
```

<!--

:CtrlPClearAllCaches

or

$ rm -rf ~/.cache/ctrlp/
-->

<br/>

## Some issues on start

<br/>

### E5248: Invalid character in group name

<br/>

(Error with plugin: vim-nerdtree-syntax-highlight)

<br/>

```
$ vi ~/.config/nvim/plugged/vim-nerdtree-syntax-highlight/after/syntax/nerdtree.vim
```

replace on

https://raw.githubusercontent.com/johnstef99/vim-nerdtree-syntax-highlight/master/after/syntax/nerdtree.vim

<br/>

### Error on execute :pyx command, ultisnips feature of coc-snippe ts requires pyx support on vim

<br/>

```
$ pip install pynvim
```

<br/>

### vim-hexokinase needs updating. Run `make hexokinase` in project root.

**On message in vim console:**

vim-hexokinase needs updating. Run `make hexokinase` in project root. See `:h he xokinase-v1-migration` for more info.

<br/>

    $ cd ~/.config/nvim/plugged/vim-hexokinase/
    $ git pull
    $ make hexokinase

<br/>

    $ sudo apt install -y xclip

    $ sudo apt install -y python3-pip
    $ pip3 install --upgrade neovim

    $ npm install -g neovim

<br/>

// coc-extensions
https://github.com/neoclide/coc.nvim/wiki/Using-coc-extensions

<br/>

### Possible can be helpful

**[Ben Awad] How to Configure Vim like VSCode [ENG, 2019]**  
https://www.youtube.com/watch?v=gnupOrSEikQ

<br/>

**init.vim:**

    $ vi ~/.config/nvim/init.vim

<br/>

https://gist.github.com/benawad/b768f5a5bbd92c8baabd363b7e79786f

<br/>

```
:PlugInstall
```

<br/>

**coc-settings.json:**

    $ vi ~/.config/nvim/coc-settings.json

<br/>

https://gist.github.com/benawad/e187dd887f256a6a002905ec7f22ad76

<br/>

### Additional Materials

**[Snowfoundry Media] Command Line: Neovim Installation and Configuration [ENG, 2020]**  
https://www.youtube.com/watch?v=ZEFXeRIFvN0

<br/>

### [Monsterlessons Academy] My Editor Setup for Web Development 2021 - Vim + Tmux

https://www.youtube.com/watch?v=YrLiugDhCuk

<br/>

### [Oleksandr Kocherhin] Neovim configs

<br/>

    $ cd ~/.config/nvim
    $ rm -rf *
    $ git clone https://github.com/wildmakaka/nvim-config .

<br/>

    $ mkdir autoload && cd autoload
    $ curl https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim -o plug.vim

<br/>

    $ mkdir -p ~/.config/nvim/plugged
    $ nvim ~/.config/nvim/init.vim

<br/>

```
:PlugInstall
```

<br/>

**How to set up Neovim 0.5 + Modern plugins (LSP, Treesitter, Fuzzy finder, etc)**  
https://blog.inkdrop.app/how-to-set-up-neovim-0-5-modern-plugins-lsp-treesitter-etc-542c3d9c9887

https://www.youtube.com/watch?v=FW2X1CXrU1w

https://github.com/craftzdog/dotfiles-public

<br/>

**Frontend Masters repo from course about vim**  
https://theprimeagen.github.io/vim-fundamentals/
