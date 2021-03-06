# vim

## 文件操作

```shell
# 在shell中使用vim打开并编辑文件
vim [file]

# 在vim中打开一个文件
:e <path/to/file>

# 在vim中保存
:w

# 在vim中另存为
:saveas <path/to/newfile>

# 保存并退出
:wq 或 :x 或 ZZ

# 不保存并退出
:q!

# 不保存退出所有正在编辑的文件
:qa!

# 切换到下一个文件标签
:bn 或 :n

# 切换到上一个文件标签
:bp 或 :p
```

## 模式切换

```shell
# 进入Insert模式
i

# 进入Insert模式, 并在光标后插入
a

# 进入Insert模式, 在当前行后插入一个新行
o

# 进入Insert模式, 在当前行前插入一个新行
O

# 进入Insert模式, 替换从光标所在位置后到一个单词结尾的字符
cw

# 退回到Normal模式
Esc
```

## 光标移动

* 仅限Normal模式下

```shell
# 左
h

# 右
l

# 上
k

# 下
j

# 移动光标到行首
0 (数字0)

# 移动光标到行尾
$

# 移动光标到本行第一个不是blank字符的位置
^

# 移动光标到本行最后一个不是blank字符的位置
g_

# 移动到下一个不包含空格单词(变量)的开头
w

# 移动到下一个不包含空格单词(变量)的结尾
e

# 移动到下一个包含空格单词(语句)的开头
W

# 移动到下一个包含空格单词(语句)的结尾
E

# 跳转到指定行
nG 或 :n

# 跳转到第一行
gg 或 1G 或 :1

# 跳转到最后一行
G

# 匹配括号移动, (, [, {, 需要先将光标移动到括号上
%

# 移动到下一个匹配的单词
*
# 移动到上一个匹配的单词
#
```

## 帮助

* 仅限Normal模式下

```shell
# 帮助
:help
```

## 编辑操作

* 仅限Normal模式下

```shell
# 剪切当前行
dd

# 复制当前行
yy 或 ddP

# 粘贴到当前行的下一行
p

# 粘贴到当前行的上一行
P

# 撤销
u

# 重做
Ctrl+r

# 搜索pattern字符串, 多个结果按n移动到下一个
/pattern

# 重复上次操作一次
.

# 重复上次操作n次, 如2dd, 3p, 100idesu [ESC], 3.
n<command>
```


## `.vimrc`配置文件

* 创建`.vimrc`作为配置文件
    - `vim`默认安装目录下有配置模板, 可以查看模板进行配置
    - 主题在`vim`目录下寻找
    - `"`: 双引号是注释

```vim
""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Displaying
""""""""""""""""""""""""""""""""""""""""""""""""""""""

" theme. Dir: /usr/share/vim/vim74/colors
colorscheme desert

" display current filename in window titlebar
set title

" display current cursor position in bottom right
set ruler

" high-light current line
set cursorline

" high-light current column
set cursorcolumn

" beautify cursor high-light
highlight CursorLine term=bold cterm=bold ctermbg=Grey guibg=Grey20
highlight CursorColumn term=NONE cterm=NONE ctermbg=Grey guibg=Grey20

" change cursor shape in different mode. 0: verticle line; 1: block; 2: und    erline
let &t_SI = "\<Esc>]50;CursorShape=1\x7"
let &t_SR = "\<Esc>]50;CursorShape=1\x7"
let &t_EI = "\<Esc>]50;CursorShape=1\x7"  " edit insert mode

" high-light search result
set hlsearch

" high-light matching quotes
set showmatch

" show line number
set number

" auto indent
set autoindent

" syntax high-light
syntax on

" indent space length
set shiftwidth=4

" backspace tab length
set softtabstop=4

" tab length
set tabstop=4

" use space instead of tab & indent
set expandtab


""""""""""""""""""""""""""""""""""""""""""""""""""""""
" File setting
""""""""""""""""""""""""""""""""""""""""""""""""""""""

" file encoding
set encoding=utf-8


""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Config
""""""""""""""""""""""""""""""""""""""""""""""""""""""

" Help language
"set helplang=cn
```


## 常见问题

* 僵死, 无法进行任何操作, 也无法切换模式
    - 可能按了`Ctrl+s`造成锁定屏幕
    - 按`Ctrl+q`解锁即可
