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
bash scripts. Every mark starts with a mark**S** and ends with a mark**E**. 
Additional, each mark starts with doulbe **@@**. Each theme in the marks is 
part of the **table of content**.

All marks are shown below:

@@todo:theme + @@todo  
@@shortcut:theme + @@shortcut  
@@command:theme + @@command
@@important:theme + @@important  
@@question:theme + @@question  
@@learned:theme + @@learned
@@link:theme + @@link  
@@bestpractice:theme + @@bestpractice  

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

## firefox:shorcuts
@@shortcut:firefox  
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
@@shortcut

@@bestpractice:firefox  
Use firefox in window1. The first tab is always *google translater* 
(german-enlgish). Your courser will always be focused in the german input 
field. You can select everything with `ctrl + a` and can type new content.  
@@bestpractice  


---------- 20231219 ----------


## markdown:syntax

@@learned:markdown  
You can create **line breaks** or go to a new line (like \<br\> in html) by 
end a line with **two or more space** and then return.  
@@learned  

@@link:markdown  
[markdown guide with cheatsheet and syntax descriptions](https://www.markdownguide.org/)  
@@link  

## firefox:bookmarks

@@bestpractice:firefox  
In the firefox *Bookmarks Menu* I added directories for each themeblock.  
@@bestpractice

## neovim:configuration

@@link:neovim  
[neovim - mainpage](https://neovim.io/)  
[neovim - build your first config file](https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/)  
@@link  

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
@@todo 

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
@@command  

- each option has a scope (eg. global)

@@question:neovim  
What is the leader key (and mapleader) an why should I use it?
@@question
@@learned:neovim  
The **leader key** (also called **mapleader**) is a way of extending the power of VIM's shortcuts by using
sequences of keys to perform a command. The default leader key is backslash. 
Most change this to comma. It is a way of creating a namespace for commands you
want to define. Vim already maps most keys and combinations of `Ctrl` + key, so 
\<leader\> is where you (or plugins) can add custom behavior. E.G.: For example,
if you find yourself frequently deleting exactly 3 words and 7 characters, you 
might find it convenient to map a command via nmap <leader>d 3dw7x so that 
pressing the leader key followed by d will delete 3 words and 7 characters. 
Because it uses the leader key as a prefix, you can be (relatively) assured 
that you're not stomping on any pre-existing behavior.  
@@learned


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
@@bestpractice

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
@@learned















