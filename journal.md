# Journal

## table of content

1. guide



## guide

### guide:about the content
This file contains my research and I will use it as my daily notebook and as 
my journal.

### guide:structure of this file
Overall this file use markdown.

### guide: marks
This file use different marks which can be searched and further processed by 
bash scripts. Every mark starts with `@@mark:theme` and ends with `@@` in the
next line. Each theme in the marks is part of the **table of content**.

All marks are shown below:

@@todo  
@@shortcut  
@@command  
@@important  
@@question  
@@learned  
@@link  
@@bestpractice  

### guide:headings
1. Headings are written in small letters.
2. Each header has the following structure: `### theme:content`

### guide:lines
Each day is marked by: -(10) date -(10)

========== CONTENT ==========

---------- 20231218 ----------

After a week of disorientation I start a new journal I tried to implement all 
the knowledge and all the ideas I collected in the past. Another mistake of 
mine was that I didn't focused me on a specific content and wanted to learn 
everthing at once. But this does not work. So my new attempt is to focus on a 
few themes. But what themes I should focus. I answered this question as 
followed. First of all I have to learn walking. What do I need to walk?

Stage 1:  
neovim  
git  
firefox  
markdown  
tmux  
i3  
Linux  
Bash  

Stage 2:  
Python  
C/C++  
Rust  
Software Development (XP Programming)  

## firefox: shorcuts
@@shortcut: firefox  
| shortcut | description |
| -------- | ----------- |
| `ctrl + t` | open a new tab |
| `ctrl + w` | close tab |
| `ctrl + l` | focus the adress bar |
| `ctrl + k` | focus address bar with defaul search engine |
| `ctrl + b` | go to bookmarks |
| `ctrl + f` | start search |
| `ctrl + \[ / \]` | go back / forward |
| `F5` | reload page |
| `ctrl + F5` | reload and override cache |
| `ctrl + tab` | cycle tabs |
| `alt + #num` | go to tab #num |
@@

@@bestpractice: firefox  
Use firefox in window1. The first tab is always *google translater* 
(german-enlgish). Your courser will always be focused in the german input 
field. You can select everything with `ctrl + a` and can type new content.  
@@


---------- 20231219 ----------


## markdown: syntax

@@learned: markdown  
You can create **line breaks** or go to a new line (like \<br\> in html) by 
end a line with **two or more space** and then return.  
@@  

@@link: markdown  
[markdown guide with cheatsheet and syntax descriptions](https://www.markdownguide.org/)  
@@  

## firefox: bookmarks

@@bestpractice: firefox  
In the firefox *Bookmarks Menu* I added directories for each themeblock.  
@@  

## neovim:configuration

@@link:neovim  
[neovim - mainpage](https://neovim.io/)  
[neovim - build your first config file](https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/)  
@@  

## neovim:set up your configuration file

[source](https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/)
- neovim's configuration file is **init.lua** and uses neovim's lua api. In 
contrast, vim's configuration file is called **vimrc**.
- There are also configuration files using **vimscript**. Vimscript is a 
language created specifically for vim.
- In Linux the configuration file init.lua is at: `~/.config/nvim/` 
- once init.lua exists we can edit it anytime by using: `:edit $MYVIMRC`

@@todo:noevim  
read and learn neovim commands (like :write, :edit, :call)
@@  

- to access neovim setting in your lua script, you have to enter the module `vim`
    - `vim.opt` has over 350 options 
    - `vim.keymap` handles the keybindings
        - basic usage: `vim.keymap.set({mode}, {lhs}, {rhs}, {opts})`
            - `{mode}`: where the keybinding should execute --> see mode
                | mode | description |
                | ---- | ----------- |
                | n | Normal mode |
                | i | Insert mode |
                | x | Visual mode |
                | s | Selection mode |
                | v | Visual + Selection |
                | t | Terminal mode |
                | o | Operator-pending |
                | '' | empty string is equivalent of n + v + o |
            - `{lhs}`: is the key we want to bind  
            - `{rhs}`: is the actio we want to execute (string, expression, or lua function)
            - `{opts}`: must be a lua table with specific properties:
                | property | description |
                | -------- | ----------- |
                | desc | A string that describes what the keybinding does |
                | remap | A boolean that determines if your keybinding can be recursive (default is `false`) |
                | bugger | Can be boolean or number. `true` == keybinding will only be effective in the current file. Number == id of an open buffer |
                | silent | A boolean. Determines whether or not the keybinding can show a message |
                | expr | A boolean. If enabled it gives the chance to use vimscript or lua to calculate the value of {rhs} |

@@command:neovim  
| command | description |
| ------- | ----------- |
| `:help option-list` | shows a list of all options |
| `:edit $MYVIMRC` | you can edit your init.lua configuration file |
| `:echo mapleader` | check the <leader> key | 
@@

- each option has a scope (eg. global)

@@question:neovim  
What is the leader key (and mapleader) an why should I use it?
@@  

@@learned:neovim  
The **leader key** (also called **mapleader**) is a way of extending the power 
of VIM's shortcuts by using sequences of keys to perform a command. The default leader key is backslash. 
Most change this to comma. It is a way of creating a namespace for commands you
want to define. Vim already maps most keys and combinations of `Ctrl` + key, so 
\<leader\> is where you (or plugins) can add custom behavior. E.G.: For example,
if you find yourself frequently deleting exactly 3 words and 7 characters, you 
might find it convenient to map a command via nmap <leader>d 3dw7x so that 
pressing the leader key followed by d will delete 3 words and 7 characters. 
Because it uses the leader key as a prefix, you can be (relatively) assured 
that you're not stomping on any pre-existing behavior.  
@@


---------- 20231220 ----------


## neovim:plugin manger

[source](https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/)

- choose a plugin manager and following their setup

## neovim: how to extend the standard config
We can extend the standard neovim config by:
1. add a **plugin** written in lua
    1. configurate this plugin via its internal options
1. add a **plugin** written in vimscript
1. use **command**: `vim.api.nvim_create_user_command({name}, {command}, {opts})`
1. use **autocommand**: `vim.api.nvim_create_autocmd({event}, {opts})` 

@@bestpractice:neovim modules  
A common convention is to put every module we create into a single folder. We do
this to avoid any potential conflict with a plugin. Add those modules in the 
init.lua by calling `require()`.
@@

@@learned:neovim require function  
`require()` only execute code once. This can be a problem if we want to reload
our config file with `:source $MYVIMRC` (the result might not be what we expect).
For that there is a little hack by empty require's cache before using it.
WARNING: This can also ends in unexpected effects.
```lua
local load = function(mod)
  package.loaded[mod] = nil
  require(mod)
end

load('user.settings') --for example
```
@@

[source](https://vonheikemen.github.io/devlog/tools/neovim-plugins-to-get-started/)

@@command:neovim  
`:set packpath?` - list all available direcotries  
`:lua vim.tbl_map(print, vim.opt.packpath:get())` - list all available 
direcotries (visual pimped)  
`:help packages` - help page for packages  
@@  

@@bestpractice:neovim plugin folder
Create a directory and where we create a **package** (a folder that contains 
several plugins. Inside this **package** we create two other folders (1) start 
and (2) opt (those plugins will only be loaded if we execute the command 
`packadd`.
@@  

@@learned: neovim plugin
We can (a) create our own plugin folders called **package**. Put the source code
inside those packages and configure the plugins by our own. Or we can use a 
**plugin manager** that handles everything for us.  
@@  

@@question: neovim plugin manager  
Which plugin manager should I use?
1. lazy.nvim
2. packer.nvim
3. paq.nvim

@@bestpractice: colorscheme
I change my terminal colorscheme via: /Edit/Properties/Unnamed/Colors:  
Text and Background Color: solarized dark  
Palette: solarized  
The colorscheme in neovim I changed via: `:colorscheme slate`  
@@  


---------- 20231221 ----------

@@question: vim shortcut
I want to write 10 similar chars in one step (eg: (10x) ----------)
How can I move one line up or down?
How can I change mulitple appearances of one word? How can I select a specific
number of appearances?
After using f (what is the other char search button) how can I move to the next
appearance of this char.
@@

@@shorcut: vim
| shortcut | description |
| -------- | ----------- |
| `N f{char}` | to the Nth occurence of {char} to the right |
| `N F{char}` | to the Nth occurence of {char} to the left |
| `N t{char}` | till before the Nth occurence of {char} to the right |
| `N T{char}` | till before the Nth occurence of {char} to the left |
| `N ;` | repeat the last "f/F/t/T" N times |
| `N ,` | repeat the last "f/F/t/T" N times in opposite direction |
| `N i {char/string} ESC` | instert {char/string} N times |
| `:s/foo/bar/g` | Find each occurrence of foo (in current line) and replace it with bar |
| `:%s/foo/bar/g` | Find each occurrence of foo (in all lines) and replace it with bar |
| `:%s/foo/bar/gc` | Change each foo to bar, but ask for confirmation |
@@

@@link: vim  
[neovim quickref](http://neovim.io/doc/user/quickref.html)  
@@  

@@learned: vim shortcut  
If you want to move a line or multi lines up or down the best way to achieve this
is by delete the line/lines (dd) and paste it/them (p/P) where you want them. In
vim there is no shortcut like in vscode `alt + up/down`.  
@@  

## linux: linuxjourney

[linuxjourney.com](https://linuxjourney.com/)  

### Command Line
- shell line: `username@hostname:current_directory` 
- everything in linux is a file. And every file is organized in a hierarchical 
directory tree.
- **absolute** vs. **relative** path: absolute path starts always with `/` (starting 
from root). Using relative paths we often work with:
| shortcut | description |
| -------- | ----------- |
| `.` | current directory |
| `..` | parent directory |
| `~` | home directory |
| `-` | previous directory |
- **Commands**: basic form: `command {flags} {arguments}`
- **Flags**: You can combine multipe flags (read from left to right *ordered*)
- `touch` is also used to change the timestamps on existing files and directories.
- **wildcard**:
| wildcar | description |
| ------- | ----------- |
| `*` | represent all single characters or strings (eg. \*.jpg) |
| `?` | represent one character |
| `[]` | represent any character within the brackets |
- when you want to copy a direcotry that contains files, you have to copy the 
directory recursively with `cp -r`.
- If you need more information about a command there are different sort of help:
    1. help or --help
    2. man
    3. whatis
-

