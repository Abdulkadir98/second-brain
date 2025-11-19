### Vim in 10 minutes

Vim is a very powerful modal text editor favored by programmers for many many years. If you need a command-line text editor then I would strongly recommend learning vim. Now, what do I mean by vim being a “modal” editor? — Vim has five modes.

1. Normal
2. Editing
3. Visual (plain, line, or block for selecting blocks of text)
4. Replace (For replacing text)
5. Command-line (For running a command)

Normal mode allows you to navigate throughout the file, perform other actions such as deletion, etc. Editing mode is self-explanatory, it allows you to insert text, and the visual mode allows you to select blocks of text and so on. You might wonder why there is need for a “mode” besides editing. What else could you possibly want to do? Remember a lot of the time coding is writing code but it’s also removing code, jumping from one function/file to another function/file, and making small edits throughout the file. The designers of vim in their infinite wisdom came up with this idea which has greatly enhanced programmers’ productivity manifold.

Let’s first start by doing the most basic thing — Opening a file in vim and closing it, the “Hello, World!” equivalent in vim if you will.

Open any shell and type `vim <filename>` . A vim editor opens. You will notice that you cannot type anything yet as it’s in normal mode. Press the`i` key to enter `insert` mode. You’ll see the word `insert` at the bottom in vim’s status bar indicating just that. After typing some text enter `esc` to exit `insert` and go back to normal mode. To exit `vim` itself you need to type in a command. A command begins with a colon `:` , to save your work and exit vim type `:wq` . The `w` saves your work and `q` closes the vim application.

**** Insert pictures ***

#### Movement

While you’re in normal mode you can navigate around a file using the arrow keys but vim provides bindings in the form of the keys `h,j,k,l` to do that.

`h` — moves the cursor to the left
`j` — moves the cursor down
`k` — moves the cursor up
`l` — moves the cursor to the right

Here are some basic vim movement actions-
###### Words

`w` — Moves the cursor to the start of the next word
`e` — Moves the cursor to the end of the next word
`b` — Moves the cursor back to the previous word

##### Lines
`0` - Moves cursor to the beginning of line
`$` - Moves cursor to the end of the line
`^` - Moves cursor to the first non-blank character

###### Screen
`H` - Top of screen
`M` - Middle of screen
`L` - Bottom of screen

##### File
`gg` - Beginning of the file
`G` - End of the file

###### Scroll
`ctrl + u` - Scroll up (Also ^ for MacOS)
`ctrl + d` - Scroll down

##### Search
`/{regex}` - Searches occurrences of regex in the file, `n/N` for navigating between matches of the regex
`f{char}` - will find the first character in the line and take the cursor to it
`t{char}` - will find the first character in the line and take the cursor just before it
After finding the first character, if you want to find the same character you can simply press the `;` key and that will repeat the last search. Vim provides lots of ways to combine two commands or compound commands into a single one. If you press `;` many times and cross the pass the character by mistake, you can perform the search in reverse and go back to the character by pressing the `,` key.

You will spend a lot of time in Normal mode. The movement commands in `Vim` are also called "nouns" because they refer to portions of text

#### Selection

Visual modes:
- `v` - visual
- `V`- visual line
- `ctrl + V` - visual block
You can use movement commands to select blocks of text.

Here's an example that I really like and use it day-to-day at my job:

When I want to move around commits in my git repository in an interactive rebase (git is explained in a later chapter)

> $ git rebase -i HEAD~3..

The default editor used by git is `vim` (another reason to learn Vim!)

```
commit 1..
commit 2..
commit 3..
```
Now if I want to move commit 3 above commit 2 I will first move the cursor to line 2 then select the entire line
```
ctrl-V + $
```
`ctrl-V` enters visual block mode and then `$` selects everything to the end of the line. You will see the entire line gets highlighted. Then press `y` (yank), this copies the text.

You can then delete the line with `dd`. Line 2 gets removed and commit 3 now becomes line 2. Then press `p` (paste), the line you just copied gets pasted after line 2. So effectively you have reordered the commits. This is what it should look like

```
commit 1..
commit 3..
commit 2..
```

You can exit the vim editor to complete the interactive rebase by typing `:wq`

#### Editing
Most of us are so used to GUIs we tend to use the mouse for everything. But with Vim everything that you use the mouse for you can use the keyboard to do it. This is where Vim really shines. By "composing" editing commands with movement commands Vim really starts resembling a programming language.

`i` - To enter `insert` mode. Allows you start typing text
`o/O` - Insert line below/above end enter `insert` mode
`d{motion}` - 'd' stand for delete. For e.g.
	- `dw` Deletes a word
	- `d$` Deletes to end of the line
	- `d0` Deletes to the beginning of line etc.
`c{motion` - 'c' stand for change. For e.g.
     - `cw` Change word, this is the equivalent of `dw` followed by `i`
`x` - Deletes a character
`s/r` - Substitute or replace a character
`y` - "Yank" or copy text, can be used along with Visual mode. Some commands like `d`also copy
`p` - Paste
`u` - Undo an action

#### Counts
Vim provides the notion of ‘count’. You can preface an “action” (moving up, left, right, and, down in this case) with an optional count telling vim the number of times you want to perform that action.

- `5j` will move the cursor below 5 lines, `4h` will move the cursor 4 positions to the left. Similarly,
- `4w` Moves four words forward
- `6dw` Deletes the next six words
you get the idea.

##### Modifiers
With the help of modifiers you can change the meaning of nouns for e.g. `i` which means "inner" or "inside" and `a` which mean "around". Navigate the cursor to to a character inside a word you wish to modify-
- `ci"` will let you change the contents of the string inside the quotes
- `ci(` similarly will let you change the contents inside the parenthesis
- `da'` deletes a single quoted string, include the surrounding quotes

#### Advanced Vim
In this section my hope is to provide a bunch of nifty commands and patterns that I find useful and hopefully you also find useful and include in your own workflows

###### Dot command (.)
The `.` command put simply, "repeats" the last change. Here "change" can be at the character level, line or lines, or even at the entire file which is what makes it so powerful.

For e.g. Consider this snippet of text
```
line one..
line two..
line three..
line four..
```
If we place our cursor at the first character and press `x` it will remove the first character. If we press `.` then it will repeat the last change i.e. remove the character under the cursor. This way, we can repeatedly remove the characters under the cursor. This example is not very helpful though. Let's look at how we can use the `.` command to perform search-and-replace of a string

###### find and replace
Remember you can use the substitute command to search for a particular regex and replace it like so,
```
:%s/regex/replacement
```
and if you want to replace all occurrences you can use the global flag to do that
```
:%s/regex/replacement/g
```
Now let's say you want selectively change each string and not perform the action on all strings. You can achieve that with the help of the `.` command! The pattern is make the change for one string, then make it repeatable with the `.` command.

<Add example paragraph here>

You can either search for the word using 
```
/target
```
or you can navigate to the word using the cursor and then press the `*` key. This will highlight all the words in the file. If you do not see them highlighted try setting it using this command
```
:set hls
```
Once our cursor is in position to change the word we perform the change with the help of the change command
```
cwreplacementString<Esc>
```
This deletes the word and replaces it with the string and then enters back to normal mode. Now we can jump to the next occurrence using the `n` key. Vim has recorded our last change which is replacing the word. So we simply use the `.` command and it performs the same change. This way we can cycle through all the words by simply hitting `n.n.n.`. 

### Customizing Vim
Vim is very configurable and maintains configuration via a "dotfile" (`~/.vimrc`) which is a plain-text file. You can easily search for example configuration files online on GitHub or various other blogs. Try not to copy-paste but understand every line in the file.


### Extend Vim
Vim has a rich plugin ecosystem with tons of cool plugins to choose from. To start using plugins create a directory where you can save the plugins
```
~/.vim/pack/vendor/start/
```
store plugins in this directory (e.g. via `git clone`)
Check out [Vim awesome](https://vimawesome.com/) for some cool vim plugins. 