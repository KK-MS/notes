# VIM tips and tricks

## 
* https://www.barbarianmeetscoding.com/boost-your-coding-fu-with-vscode-and-vim/moving-blazingly-fast-with-the-core-vim-motions/

* Sample vimrc file

<details> <summary> Click for sample .vimrc </summary>

```
"#####################################################################################(

call plug#begin()

" List your plugins here
Plug 'tpope/vim-sensible'

" Shorthand notation for GitHub; translates to https://github.com/junegunn/seoul256.vim.git
Plug 'junegunn/seoul256.vim'

" Any valid git URL is allowed
Plug 'https://github.com/junegunn/vim-easy-align.git'

" On-demand loading: loaded when the specified command is executed
Plug 'preservim/nerdtree', { 'on': 'NERDTreeToggle' }

"  A Git wrapper so awesome, it should be illegal
Plug 'tpope/vim-fugitive'

" Colorscheme
" solarized
Plug 'altercation/vim-colors-solarized'

call plug#end()
"#####################################################################################)


" Color schemes should be loaded after plug#end().
" We prepend it with 'silent!' to ignore errors when it's not yet installed.
silent! colorscheme seoul256

" Terminmal or GUI based vim
" If terminal use
" :set termguicolors
" If GUI or terminal that supports palette
" :set notermguicolors

" KKMS
set ts=4
set sw=4
set expandtab
set hlsearch

```

</details>
