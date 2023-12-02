# Research

This document contain my research about the themes:

1. DataScience
2. Software Development
3. Consulting
4. IT-Security
5. Programming Languages
6. Linux
7. All other stuff

## 20231128

Today I am starting my journey. The first steps that come to mind are those
that will enable me to travel secure. Those steps are:
1. vim
2. git
3. terminal
4. english
5. Collecting best_practice and short_cut

These points are the minimum requirement. And I'm now starting to acquire 
these points.

@best_practice: While writing in english. Terminal with VIM in window2 and
Firefox in window1. In Firefox open google Translate (german-english). You can
switch between windows with (using i3-wm) [i3-cmd + 1]. Your curser will 
always be focused in the german input field. Use [ctrl + a] to select all and 
you can type the new text. You can switch back to vim with [i3-cmd + 2]

@short_cut:
Firefox: open a new Tab: [ctrl + t]
Firefox: close tab : [ctrl + w]
Firefox: focus the search bar:
Firefox: focus adress bar : [ctrl + L]
Firefox: go back / go forward : [ctrl + [ | ]]
Firefox: reload : [F5] 
Firefox: reload and override cache: [ctrl + F5]
Firefox: focus address bar with defaul search engine: [ctrl + k]
Firefox: cycle tabs (recently used order): [ctrl + tab]
Firefox: cycle tabs (in tab order) : [ctrl tab | shift-tab]
Firefox: go to tab 1-8 : [alt + x]


@ToDo: writing my own VSCode extension: combining vim with standard short_cuts
(e.g. : while using vim extension the standard short_cut for selecting
everything [ctrl + a] do not work. 

@ToDo: every day start with 10 min shortkey learning routine. That means
1. Check the short_cuts and the best_practive from last session and just train
them so that they become muscle memory.

## VIM
In this chapter I want to collect vim short_cuts. Afterwards I have to create
a cheat sheet for faster and better training.

In general you can distinguish different themes in vim shortcuts - those will 
be represented by the following headers:

### Cursor Movement
#### General
Standard curser movement: h, j, k, l
[u] - undo
[ctrl + r] - redo
[:w] - save the file, but don't quit
[:wq] - save the file and quit
[:q] - quit (fails if anything has changed)
[:!q] - quit and throw away changes
[.] - repeat last command
#### Horizontal
[w] - Jumping to the next word-start
[W] - Jumping to the next word-start (space seperated)
[e] - Jumping to the next word-end == end of current word
[b] - Jumping to the least word-start == beginning of current word
[B] - Jumping to the least word-start (space seperated)
[0] - Jumping to the start of the line
[0w] - Jumping to the first non-blank character of the line
[$] - Jumping to the end of the line
[XX + w] - Jumping XX times to the next word-start
[XX + e] - Jumping XX times to the next word-end
[XX + b] - Jumping XX times to the least word-start
#### Vertical
[gg] - Jumping to the start of the file
[G] - Jumping to the end of the file
[H] - Jumping directly to the top of the screen
[M] - Jumping directly to the middle of the screen
[L] - Jumping directly to the bottom of the screen
[Ctrl + b] - Moving one fullscreen forward
[Ctrl + f] - Moving one fulsscreen backward
[:XX] - Jumping to line XX
[XX + j/k] - Jumping XX lines down/up
[}] - go forward by paragraph (the next blank line)
[{] - go backwards by paragraph (the next blank line)
#### Character search
[f + char] - move forward to the given char
[F + char] - move backward to the given char
[t + char] - move forward to before the given char
[T + char] - move backward to before the given char
[; | ,] - repeat search forwards | backwards
[%] - jumps between matching () or {}
#### Screen movement
[Ctrl + e] - Moving the screen down one line without cursor movement
[Ctrl + y] - Moving the screen up one line without cursor movement
### Insert mode
#### Enter insert mode
[i] - Inserting before the cursor
[I] - Inserting at the start of the line
[a] - Inserting after the cursor
[A] - Inserting at the end of the line
[o] - Opening a new line below the selected line + Inserting
[O] - Opening a new line above the selectedd line + Inserting
[ea] - Inserting at the end of the selected word
[bi] - Inserting at the start of the selected word
#### While in insert mode
[ctrl + h] deleting the character before the cursor
[ctrl + w] deleting the word before the cursor 
[ctrl + j] takes the rest of the line to the next line
[ctrl + t] moving line content right one line shift width
[ctrl + d] moving line content left one line shift width
### Cut & Paste
[yy] - pull(copy) a single line
[XX + y] - pull XX single lines
[yiw] - pull the word below the cursor
[yaw[ - pull the word below the cursor and add space
[p] - paste from clipboard after the cursor position
	- words are added in same line
	- lines are added before/after current line
[P] - paste from clipboard before the cursor position
[dd] - deleting a line - pull it to clipboard
[XX + dd] - deleting XX lines - pull them to clipboard
[dw] - deleting the characters until the next word-start
[db] - deleting the characters until the least word-start
[de] - deleting the characters until the next word-end
[diw] - deleting the whole word under the cursor
[D] - deleting cursor and the rest of the line
[x] - deleting character
[XX + x] delecting XX characters
### Editing
[r] - replacing one character
[R] - replacing multi single characters
[J] - Joining current line with line below with adding one-line space
! Difference between changing and deleting. Changing contains to insert insert
mode at the end of the command.
[cc] - changing the entire line
[C] - changing the end of the line
[ciw] - replacing an entire word
[cw] - Replacing until the next word-start
[ce] - Replacing until the next word-end
[cb] - Replacing until the least word-start
[s] - deleting characters along with substituting their text
[S] - deleting lines along with substituting their text
[xp] - Transposing 2 letters
### Search and replace
[/yyyy] - search pattern yyyy
[?yyyy] - search backwards for pattern yyyy
[n] - repeating search in similar direction
[N] - repeating search in opposite direction
[\*] - next whole word under the cursor
[#] - previous whole word under the cursor
[:%s/old/new/g] -  replacing old content with the new ones
[:%s/old/new/gc - replacing all old with new with confirmations
### Visual mode
[v] - start visual mode
[V] - start linewise visual mode
[ctrl + v] - start visual block mode
#### In visual mode
[d | x] - delete selection
[s] - replace selection
[y] - yank selection
#### System clipboard
["\*p | "+p] - paste form the clipboard
["\*y | "+y] - paste to clipboard

## 20231130

Today I start learning about git and github.

### GitHub

First, I will create a new private repository. This would be the similiar to
this directory "cjteclab".

## 20231201

### GitHub
What is important to know about git and github?
What is daily business by using git/github?
1. First steps with git and github
	- set username
	- set commit email address
1. How to connect your remote computer with github?
	- clone via https
	- clone via ssh
	- @[computer_science] ssh
1. Daily work with git/github
	- pull / push
	- branching
	- merges
	- add / commit - routine
	- checkout history : and go back to early stage
1. How to work with open source projects
	- fork
	- pull request
1. Repository ingredients
	- gitignore
	- community health files : https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file
	- licences ( add licence when creating a public repository from a fork
### Reading GitHub docs to get better overview
#### Get started / get started
- apply 2FA (2FactorAuthentication)
- @ToDo check out markdown cheatsheet: https://www.markdownguide.org/cheat-sheet/
- @best_practice: always use a README.md in a directory/repository
- branch:
	- use branches to test and add new features
	- at the end you have to merge a branch into main-branch (also called committing)
	- branches is like making a copy/snapshot of the current state
	- branches can pull updates from main
	- you have to delete the branch after merged
- commits : def: saved changes
	- each commit has a message: why a change was made
- pull request:
	- heart of collaborating on GitHub. Resquesting, that someone review 
and pull your contribution and merge them into their branch.
	- need: title and description
- @ToDo : check out 'GitHub Skills courses'
- clone : creating a local copy on your computer
- Fork : a new repository based on the original one.
- Fork VS branch VS clone
	- branch vs fork: 
		 A repository code branch, like a branch of a tree, remains part of the original repository. The code that is branched (main trunk) and the branch know and rely on each other.
Fork is another way of saying clone or copy. So, unlike a branch, a fork is independent from the original repository. If the original repository is deleted, the fork remains. If you fork a repository, you get that repository and all of its branches.
	- clone vs. fork:
		fork creates a completely indepented copy of Git repository. A clone in contrast creates a linked copy that will continue to synchronize with the target repository.
- Fetch vs. pull
	- pull == fetch + merge , while fetch only update without merge

### Markdown

## 20231202

### Git commands

### Learning strategy
I have to adopt my learning strategy. In the past I always wrote down every
command or every shortcut. But then I never used the notes, because I searched 
the internet for the right answer. So it makes no sense to write down commands.

But what does make sense?

1. Knowing what possibilities you have (in a logic way) and what you may can 
do? **Functional knowledge**

2. Where you can find information? **Locational knowledge** 
  1. Using commands like **help** and **manual pages**
  2. Internet : Important bookmarks, stackoverflow
  3. Advanced : Forums

3. Collecting commands and other things I active using **Actional knowledge**

### Bash scripting

- Each script starts with the line: `#!/bin/bash`
- 3 file descriptors (3 return values): stdin(0), stdout(1), stderr(2)
- redirection outputs *>*
  - there a some combination between stdout & stderr
    - redirect stdout to stderr and vise-versa: *a>&b* -> link a to b 
    - redirect both to stderr or stdout
    - redirect both to a file: *>&*
- pipes : use the output of a program as the input of another one : *|*
@ToDo : get a collection of bash commands (eg. echo, sed)
- variables
  - have no datatype
  - can contain a number(only int), character, string
  - you get the value of the variable by writing: "*$*variable"
  - you can define local variables: `local [variable]=value
- functions
  - `function [name] {}
  - call a function by only typing its name
  - handling arguments is a little bit strange, parameters in the function def do not exist.
    - in function body: *$1* -> means take the first argument
    - arguments are set by: `[function_name] argument

