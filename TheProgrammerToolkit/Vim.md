### Vim in 10 minutes

Vim is a very powerful modal text editor favored by programmers for many many years. If you need a command-line text editor then I would strongly recommend learning vim. Now, what do I mean by vim being a “modal” editor? — Vim has five modes.

1. Normal
2. Editing
3. Visual (plain, line, or block for selecting blocks of text)
4. Replace (For replacing text)
5. Command-line (For running a command)

Normal mode allows you to navigate throughout the file, perform other actions such as deletion, etc. Editing mode is self-explanatory, it allows you to insert text, and the visual mode allows you to select blocks of text and so on. You might wonder why there is a need for a “mode” besides editing. What else could you possibly want to do? Remember a lot of the time coding is writing code but it’s also removing code, jumping from one function/file to another function/file, and making small edits throughout the file. The designers of vim in their infinite wisdom came up with this idea which has greatly enhanced programmers’ productivity manifold.

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

You will spend a lot of time in Normal mode. The movement commands in `Vim` are also called "nouns" because they refer to portions of text

#### Editing
Most of us are so used to GUIs and we tend to use the mouse for everything. But with Vim everything that you use the mouse for you can use the keyboard to do it. This is where Vim really shines. By "composing" editing commands with movement commands Vim really starts resembling a programming language.

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

For example:

`5j` will move the cursor below 5 lines, `4h` will move the cursor 4 positions to the left. Similarly,
- `4w` Moves four words forward
- `6dw` Deletes the next six words
you get the idea.




