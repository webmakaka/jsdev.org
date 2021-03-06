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

**<a href="/env/nodejs/">Nodejs should be installed</a>**

<br/>

**Install Golang (some plugins need golang) (Optional)**  
https://golang.org/doc/install

<br/>

<br/>

### Step 1. Setup

    $ mkdir ~/apps && cd ~/apps
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

    // I also decided to add aliases in the bottom of file
    $ sudo vi /etc/bash.bashrc

```
alias vi='nvim'
alias vim='nvim'
```

<br/>

    $ vi --version
    NVIM v0.4.4

<br/>

### Install Additional fonts and icons

**ryanoasis/vim-devicons**

https://github.com/ryanoasis/vim-devicons

<br/>

    $ cd ~/tmp
    $ git clone --depth 1 https://github.com/ryanoasis/nerd-fonts
    $ cd nerd-fonts
    $ ./install.sh

<br/>

### Install package manager for neovim (Vim Plugins)

https://github.com/junegunn/vim-plug

<br/>

    $ mkdir -p ~/.config/nvim/ && cd ~/.config/nvim/
    $ mkdir autoload && cd autoload
    $ curl https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim -o plug.vim

<br/>

    $ mkdir -p ~/.config/nvim/plugged
    $ vi ~/.config/nvim/init.vim

<!--

:CocList

call CocAction('runCommand', 'tsserver.organizeImports')

-->

<!--

command! -nargs=0 OR :call CocAction('runCommand', 'editor.action.organizeImport')

-->

<br/>

```js
set number
set scrolloff=8
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

Plug 'scrooloose/nerdtree'
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'tiagofumo/vim-nerdtree-syntax-highlight'

Plug 'neoclide/coc.nvim', {'branch': 'release'}
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

### Some issues on start

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

### [Oleksandr Kocherhin] Neovim configs

<br/>

    $ cd ~/.config/nvim
    $ rm -rf *
    $ git clone https://github.com/webmak1/nvim-config .

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

**Frontend Masters repo from course about vim**  
https://theprimeagen.github.io/vim-fundamentals/

<br/>

### Additional Materials

**[Snowfoundry Media] Command Line: Neovim Installation and Configuration [ENG, 2020]**  
https://www.youtube.com/watch?v=ZEFXeRIFvN0
