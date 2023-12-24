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
@@keybinding  
@@command  
@@important  
@@question  -- @@ answer
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
@@keybinding: firefox  
| keybinding | description |
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

@@important: markdown  
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
                | remap | A boolean that determines if your keybinding can be 
                recursive (default is `false`) |
                | bugger | Can be boolean or number. `true` == keybinding will 
                only be effective in the current file. Number == id of an open buffer |
                | silent | A boolean. Determines whether or not the keybinding 
                can show a message |
                | expr | A boolean. If enabled it gives the chance to use 
                vimscript or lua to calculate the value of {rhs} |

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
@@answer:  
The **leader key** (also called **mapleader**) is a way of extending the power 
of VIM's keybindings by using sequences of keys to perform a command. The default leader key is backslash. 
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

@@important:neovim require function  
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

@@important: neovim plugin
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

@@question: vim keybinding
I want to write 10 similar chars in one step (eg: (10x) ----------)
How can I move one line up or down?
How can I change mulitple appearances of one word? How can I select a specific
number of appearances?
After using f (what is the other char search button) how can I move to the next
appearance of this char.
@@answer
@@keybinding: vim
| keybinding | description |
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
@@  

@@link: vim  
[neovim quickref](http://neovim.io/doc/user/quickref.html)  
@@  

@@important: vim keybinding  
If you want to move a line or multi lines up or down the best way to achieve this
is by delete the line/lines (dd) and paste it/them (p/P) where you want them. In
vim there is no keybinding like in vscode `alt + up/down`.  
@@  

## linux: linuxjourney

[linuxjourney.com](https://linuxjourney.com/)  

### Command Line
- shell line: `username@hostname:current_directory` 
- everything in linux is a file. And every file is organized in a hierarchical 
directory tree.

@@important: linux  
Everything in linux is a file. And all files are organized in a hierarchical 
directory tree.
@@  

- **absolute** vs. **relative** path: absolute path starts always with `/` (starting 
from root). Using relative paths we often work with:
| keybinding | description |
| -------- | ----------- |
| `.` | current directory |
| `..` | parent directory |
| `~` | home directory |
| `-` | previous directory |
- **Commands**: basic form: `command {flags} {arguments}`
- **Flags**: You can combine multipe flags (read from left to right *ordered*)
- `touch` is also used to change the timestamps on existing files and directories.
- **wildcard**:
| wildcard | description |
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

---------- 20231222 ---------- 

## linux: linuxjourney

[linuxjourney.com](https://linuxjourney.com/)  

### Linux : less navigation

@@keybinding: less navigation
| keybinding description |
| ---------- ----------- |
| `q` | quit out of less and go back to shell |
| `{up}/{down}` | nagivate up or down |
| `g` | move to beginning of file |
| `G` | move to end of file |
| `/{search}` | search for specific text |
| `h` | help, while you are in less |
@@

@@command: bash help options
| command | description |
| ------- | ----------- |
| `help` | some help pages can be entered by `help {command}` others by `{command} --help` |
| `info` | some info pages can be entered by `info {command}` others by `{command} --info` |
| `man` | manual pages - can be entered by `man {command} |
| `whatis` | short description of the command - entered by `whatis {command}` |
@@  

## linux: linuxjourney: Chapter Text-Fu

- Processes use I/O streams to receive input and return output. 


---------- 20231223 ----------


## linux: linuxjourney

### linux: $PATH
@@important: linux $PATH  
$PATH containts a **list of paths** (separated by colon) that the system searches
when it runs a command. If the path is not in $PATH the executable file can't be
called by `$ {command}`.
@@  

### linux: linuxjourney - chapter: user management

- any traditional operating system have **users** and **groups**.
    - the system manage users by **user ids (UID)** (not username).
        - mapping between UID and username is mapped in: `/etc/passwd`
        - **ATTENTION**: every process is associated with 3 UIDS: (1) effective
        user ID (2) real user ID (3) saved user ID.
    - the system manage groups by **group ID (GID)**
        - mapping between GID and groupname is mapped in: `etc/group`
- in most linux distribution every user has its own **home directory** and is 
usually located in `/home/username`
- Linux has additional users that use the system:
    1. system daemons: they continuously run processes to keep the system functioning.
    2. root/superuser: has all permissions and accesses
- **sudo**: the file `etc/sudoers` lists users who can run sudo and can be edited
by using the command `visudo`.
- `ect/passwd` contains rows in the form `root:x:0:0:root:/root:/bin/bash`. Meaning
of the fields:
| field | description |
| ----- | ----------- |
| 1 | username |
|2 | User's password - the password is not really stored in this file, it's
usually stored in the /etc/shadow file. The symbol **x** stands for: 'password is
stored in /ect/shadow'. The symbol **/*** stands for: 'the user doesn't have login
access'. The symbol **{blank}** stands for: 'user doesn't have a password'. |
| 3 | user ID |
| 4 | group ID |
| 5 | GECOS field: comments about the user (real name, phonenumber etc.) - comma delimited |
| 6 | user's home directory |
| 7 | user's shell |
- `ect/shadow` stores information about user authentication. Contains rows in the
form: `root:MyEPTEa$6Nonsense:15000:0:99999:7:::`
    - Most distribution today, user authentication doesn't rely on just the 
    /etc/shadow file. There are other mechanisms (PAM etc.) that replace authentication.
- **User Management Tools**: commands: useradd, userdel, passwd

### linux: linuxjourney - chapter: file permission

- **file permission** has four parts e.g.: `drwxr-xr-x` --> ` d | rwx | r-x | r-x  `
    1. The first char represent the **filetype** (d == directory, - == regular file)
    2. **user permissions**
    3. **group permission**
    4. **other permissions**
- Meaning of the characters:
| character | meaning |
| --------- | ------- |
| `r` | readable |
| `w` | writable |
| `x` | executable |
| `-` | empty |
- **change permission** with `chmod`. There are 2 methods to change permission.
    1. Using operators **+**(add) and **-**(remove): eg: u+x (add x to user)
    2. Using **numerical format**: this method allows to change permission all at once.
        - | number | numerical representation |
          | ------ | ------------------------ |
          | 4 | read permission |
          | 2 | write permission |
          | 1 | execute permission |
        - Example `$ chmod 755 myfile`
            - 7 = 4 + 2 + 1 : read, write and execute for user
            - 5 = 4 + 1 : read and execute for group
            - 5 = 4 + 1 : read and execute for other
- **change ownership** by using `chown` (user ownership) and `chgrp` (group ownership)
    - you can modify both at the same time with: `$ sudo chown username:groupname file`
- **Set User ID (SUID)** and **Set Group ID (SGID)**: Allows to run a program as
the owner of the program file rather than as themselves. 
@@important: linux SUID and SGID  
SUID and SGID only apply to execution of files (the x in file permissions)
@@  
    - **SUID** is reptesented by the bit `s`. Can be modified by `u+s` or by 
    **pre-pended** `4` to the permission set (eg: `$ sudo chmod 4755 myfile`).
- **The Sticky Bit**: This permission bit, "sticks a file/directory" this means
that only the owner or the root user can delete or modify the file. The sticky
bit is represented by a `t` at the end of the **file permission** (eg: `drwxrwxrwxt`).
    - the sticky bit can be modified by `+t` or **pre-pended** `1` (eg: `$ sudo chmod 1755 mydir`).

### linux: linuxjourney - chapter processes

- processes are managed by the kernel
- each process has a **process ID (PID)**. The pid is assigned in the order that
processes are created.
- `$ ps` print a list of running processes. The following infos a print
| shortcut | description |
| -------- | ----------- |
| PID | Process ID |
| TTY | Controlling terminal associated with the process |
| STAT | Process status code |
| TIME | Total CPU usage time |
| CMD | Name of executable/command |
- `$ top` is similar to `ps` but it gives you a real time information about the 
processes instead of of a snapshot. By default it will be refreshed every 10 seconds.

#### Controlling Terminal (TTY):
There are two types of terminals:
    - **regular terminal devices**: 
    - **pseudoterminal devices**: they emulate terminals with the shell terminal
    window and are denoted by PTS.
    - Processes are usually bound to a controlling terminal. (Personal experience:
    start a program with the shell. By closing the shell the program will also be 
    closed). But there are processes (eg. daemon processes) that are essentially
    keeping the system running. Those processes we don't want to get terminated
    when closing a terminal. Those processes have no TTY and in the `ps` output
    they are listed with **?**.

#### Process Details
In general a process is a running program on the system. The
system allocate (1) memory, (2) CPU, (3) I/O to make the system run. A process is 
an **instance** of a running program.
    - The **kernel** handles all processes. It loads up the code of a program in 
    memory, determines and allocates resources and keeps track (status, resources,
    owner, signal handling, etc) of the process. Also the **kernel** handles the task
    that every process gets the right amount of resources on the process demands.

#### Process Creation
When a new process is created, an existing process basically
clones itself using something called the **fork system call**. The **fork system call**
creates a mostly identical **child process**, this child process takes on a new 
process ID (PID) and the original process becomes its **parent process** and has
something called a **parent process ID (PPID)**. Afterwards, the child process 
can either continue to use the same program its parent was using before or more
often use the execve system call to launch up a new program. This system call 
destroys the memory management that the kernel put into place for that process 
and sets up new ones for the new program.
    - every process hat to have a parent and they are just forks of each other.
    - **Mother of all processes**: When the system boots up, the kernel creates a
    process calles **init** (PID == 1). The init process can't be terminated unless
    the system shuts down. It runs with root privileges.

#### Process Termination
A process can exit using the **_exit system call**, this
will free up the resources that process was using for reallocation. So when a 
process is ready to terminate, it lets the kernel know why it's terminating with
something called a **termination status**. Most commonly a status of 0 means that the
process succeeded. However, that's not enough to completely terminate a process.
**The parent process has to acknowledge the termination of the child process by using
the wait system call** and what this does is it checks the termination status of 
the child process. **But** there is another way to terminate a process: **signals**.
    - Based on the termination of a process there are some extra types:
        - **Orphan Processes**: When a parent process dies before a child process,
        the kernel knows that it's not going to get a wait call, so instead it makes
        these processes "orphans" and puts them under the care of init. Init will
        eventually perform the wait system call for these orphans so they can die. 
        - **Zombie Processes**: What happens when a child terminates and the parent
        process hasn't called wait yet? We still want to be able to see how a child
        process terminated, so even though the child process finished, the kernel
        turns the child process into a zombie process. The resources the child 
        process used are still freed up for other processes, however there is 
        still an entry in the process table for this zombie. Zombie processes also
        cannot be killed, since they are technically "dead", so you can't use 
        signals to kill them. Eventually if the parent process calls the wait 
        system call, the zombie will disappear, this is known as "reaping". If the
        parent doesn't perform a wait call, init will adopt the zombie and 
        automatically perform wait and remove the zombie. It can be a bad thing
        to have too many zombie processes, since they take up space on the process
        table, if it fills up it will prevent other processes from running.

#### Signals
*A signal is a notification to a process that something has happened*.
    - When a signal is **delivered**, a process can do a multitude of things:
        1. ignore the signal
        2. *catch* the signal and perform a specific handler routine
        3. process can be terminated - as opposed to the normal exit system call
        4. block the signal
    - **Common Signals**: Each signal is defined by integers with symbolic names 
    with the fomr `SIGxxx`:
    | signal | meaning | description |
    | ------ | ------- | ----------- |
    | SIGHUP / HUP / 1 | Hangup | sent to a process when the controlling terminal is closed |
    | SIGINT / INT / 2 | Interrupt | You can use `Ctrl-C` and the system will 
    try to gracefully kill the process |
    | SIGKILL / KILL / 9 | Kill | Kill the process, kill it with fire, doesn't do any cleanyp |
    | SIGSEGV / SEGV / 11 | Segmentation fault |
    | SIGTERM / TERM / 15 | Software termination | kill the process, but allow it
    to do some cleanup first |
    | SIGSTOP / STOP | Stop | stop/suspend a process |
        - Numbers can vary with signals so they are usually reffered by their names.
        - Some singnal are unblockable (eg. SIGKILL)

#### Kill (terminate)
A kill signal will terminate the process. 
    - You can also specify a signal with the kill command: `$ kill -9 12455`

#### niceness
- Processes can't run at the same time. So processes use the CPU for a small amount
of time called **time slice**. By default, the kernel handles all of these time slices
and switching between the running prcesses. Processes aren't able to decide when
and how long they get CPU time, if all processes behaved normally they would 
each (roughly) get an equal amount of CPU time. However, there is a way to influence
the kernel's process scheduling algorithm: **niceness**.
    - Processes have a number to determine their priority for the CPU. A high number
    means the process is nice and has a lower priority for the CPU and a low or
    negative number means the process is not very nice and it wants to get as much
    of the CPU as possible.
    - Change the **niceness** level for a **new process**: `$ nice -n 5 apt upgrade`
    - Change the **niceness** level for a **existing process**: `$ renice 10 -p 3245`

#### Process States
Most common states of a process:
| state | description |
| ----- | ----------- |
| R | running or runnable, it is just waiting for the CPU to process it |
| S | Interruptible sleep, waiting for an event to complete, such as input from the terminal |
| D | Uninterruptible sleep, processes that cannot be killed or interrupted with a 
signal, usually to make them go away you have to reboot or fix the issue |
| Z | Zombie, we discussed in a previous lesson that zombies are terminated 
processes that are waiting to have their statuses collected |
| T | Stopped, a process that has been suspended/stopped |

#### Where are process information stored?
- Because everything in Linux is a file, so processes are also files. They are stored
in a special filesystem **/proc**:
    - Each **PID** has its own sub-directory.
- The **/proc** directory is how the kernel is views the system.

#### Job Control
1. **Sending a job to the background** by appending an ampersand (&).
`$ sleep 1000 &`
2. **View all background jobs**: 
`$ jobs`
    - The **+** next to the job ID means that it is the most recent background job
    that started. The job with the **-** is the second most recent command.
3. **Sending a job to the background on existing job**
Fist suspend the job with `Ctrl-Z` and then run the `bg` command to send it to the 
background.
4. **Moving a job from the background to the foreground**: 
`$ fg` for the most recent background job (the one with a +) or `$ fg %1` (for the job ID)
5. **Kill a background job** `kill %1`.

3. 
