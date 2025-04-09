## VIM tips and tricks

### vim turotials
  * https://www.barbarianmeetscoding.com/boost-your-coding-fu-with-vscode-and-vim/moving-blazingly-fast-with-the-core-vim-motions/

### VIM plugin
* Ref: https://github.com/junegunn/vim-plug
* download plug.vim at autoload directory
  ```sh
  mkdir -p ~/.vim/autoload
  cd ~/.vim/autoload/
  wget https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  ```
* Plug frequently used commands
  * Install/update: `:PlugInstall` or `PlugUpdate`, to install or update the plugins
  * Clean: `:PlugClean`, to remove plugins no longer in the list
* Make sure that you're tackling the right problem by breaking down the startup time of Vim using --startuptime.
  ```sh
  vim --startuptime /tmp/log
  ```
* After change in .vimrc,
  * run `:so ~/.vimrc` or `:source ~/.vimrc` to load the change without closing and opening .vimrc
  * run `PlugInstall`

### Sample .vimrc file

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

" Tagbar: a class outline viewer for Vim
" Tagbar is a Vim plugin that provides an easy way to browse the tags of the
" current file and get an overview of its structure. It does this by creating a
" sidebar that displays the ctags-generated tags of the current file, ordered
" by their scope. This means that for example methods in C++ are displayed
" under the class they are defined in.
Plug 'preservim/tagbar'

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
