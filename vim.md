# TODO
## save load session splits
## Export all shortcut keys
## find file list
http://vim.wikia.com/wiki/Find_files_in_subdirectories

# blank horizontal split
new
# current buffer
enew
# blank vertial split
vnew
# custom quickfix window qf
:cexpr systemlist("find . -type f -name '*.vim'")

# script
## get current buffer number
bufnr('%')
## get window/split number
bufwinnr(bufnumber)
## Move to specified split
execute l:window_number . "wincmd w"
## get name from buffer number
echo bufname(1)

# variable scope
g:var - global.
a:var - function argument.
l:var - local to function.
b:var - local to buffer.
w:var - local to window.
t:var - local to tab.
v:var - Predefined by Vim.
s: prefix is designed to limit the scope to the current script
\#: is designed for autoloading exported functions (that is, functions that are available outside the current script).
Use either just s:name (if you only need it to be available from the current script) or filename#name (if you want to call it from other scripts).
:help write-library-script and :help local-function.

# shortcuts
vi{}() select bracket block


:set number!
:set number?
Mapping keys is one of the places where Vim comments don't work.
When you press the space bar now, Vim thinks you want it to do what viw<space>"<space>Select<space>word would do. Obviously this isn't what we want.

:nnoremap <buffer> Q x
:autocmd BufNewFile,BufRead *.html setlocal nowrap
:autocmd FileType javascript nnoremap <buffer> <localleader>c I//<esc>
:autocmd FileType python     nnoremap <buffer> <localleader>c I#<esc>

:augroup testgroup
:    autocmd!
:    autocmd BufWrite * :echom "Cats"
:augroup END

:normal! gg/a<cr>

# Set Options
:set tabstop=4 <=> :let &tabstop=4
## take effect only to cur buffer
:let &l:tabstop=4

:set textwidth=80
:echo &textwidth

:let &textwidth = &textwidth + 10
:set textwidth?

:let &l:number = 1

# Registers
let @a = "hello!"
echo @a

# view 视图
winsaveview() winrestview()
let qfview = winsaveview()
call winrestview(qfview)

# timestamp
echo strftime("%Y-%m-%d %H:%M:%S")

# get path by filename
fnamemodify
## relative path to work dir
fnamemodify(self.str(), ':.')
:h filename-modifiers

# uninstall
brew uninstall --force macvim
brew cleanup
brew uninstall --force python@2
brew link --overwrite python
brew install macvim --with-cscope --with-lua --with-python --override-system-vim

# current version 自编译版
https://github.com/macvim-dev/macvim
## work with python3
brew tap macvim-dev/macvim
brew install --HEAD macvim-dev/macvim/macvim

