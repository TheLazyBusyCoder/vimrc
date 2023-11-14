# This is my vimrc :) 

<code>

" Enable Vundle
set nocompatible
filetype off
set rtp+=~/_vimfiles/bundle/Vundle.vim

" Start Vundle
call vundle#begin()
Plugin 'sickill/vim-monokai'
Plugin 'tpope/vim-surround'
Plugin 'jiangmiao/auto-pairs'
Plugin 'scrooloose/nerdcommenter'
Plugin 'itchyny/lightline.vim'
call vundle#end()

" Set options
filetype plugin indent on
set belloff=all
set tabstop=4
set shiftwidth=4
set mouse+=a
set guioptions -=m
set guioptions -=T
set nobackup
set nowb
set noswapfile
set smarttab
set ai
set si
set wrap
set showcmd
set wildmenu
set showmatch

" Vim text appearance
syntax on
colorscheme monokai
set guifont=JetBrains_Mono_Medium:h16:W500:cANSI:qDRAFT

" Key mappings
inoremap jk <esc>
set nu
vnoremap <C-c> "+y
map <C-v> "+p

" NERDCommenter mappings
nmap <C-/> <Plug>NERDCommenterToggle
vmap <C-/> <Plug>NERDCommenterToggle

" Custom file type settings
autocmd FileType python setlocal tabstop=4 shiftwidth=4 expandtab
autocmd BufRead,BufNewFile *.js setlocal filetype=javascript

" Compiler and interpreter mappings
autocmd filetype cpp nnoremap <F9> :w <bar> exec '!g++ '.shellescape('%'). ' && ./a.out '<CR>
autocmd filetype c nnoremap <F9> :w <bar> exec '!gcc '.shellescape('%'). ' && ./a.out '<CR>
autocmd filetype java nnoremap <F9> :w <bar> exec '!java '.shellescape('%'). '' <CR>
autocmd filetype python nnoremap <F9> :w <bar> exec '!python '.shellescape('%'). '' <CR>
autocmd filetype javascript nnoremap <F9> :w <bar> exec '!node '.shellescape('%'). '' <CR>

set backspace=indent,eol,start
set encoding=utf-8

" Snippets
" nnoremap <C-j> iclass <ESC>"%pxxxxxa {<ESC>opublic static void main(String args[]){<Esc>o<Esc>o}<Esc>o}<Esc>kki<Tab><Tab>

iab class class <ESC>"%pxxxxxa {<CR>public static void main(String args[]) {<CR>
iab sysout System.out.println();
iab for for <ESC>"%i() {<CR>}<ESC>O
iab main public static void main(String args[]) {<CR>

</code>
