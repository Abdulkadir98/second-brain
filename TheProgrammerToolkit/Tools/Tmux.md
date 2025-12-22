Tmux is an abbreviation for **T**erminal **M**ultiplexer. It allows you to run multiple programs simultaneously in a single terminal session. It easily lets you switch between programs and "detach" a program from a "window", allowing the program to run in the background. A good analogy to what Tmux does for the command-line is what the Desktop GUI does for applications on your computer.

Here's what TMUX mainly allows you to do:
1. Multitasking - Run multiple applications in the same terminal window. Some common scenarios-
	1. Have one main window with Vim/Emacs or any other text editor, another window to run and build the program
	2. Run `$ tail -F /var/log/apache/error.log` to watch the live stream of events
	3. Have a separate window that is ssh'd into a cloud server
2. Run applications in the background - You can "detach" a tmux "session", to allow running the process in the background, and then "re-attach" the session to bring the process back to the foreground. It is useful in these cases-
	1. Local machines - You start all your applications within a tmux session inside your terminal. If you accidentally exit out of the terminal, you can restart the terminal and simply re-attach the tmux session without losing any work on the tasks that were running. Clicking 'x' on the terminal will not kill the tmux session
	2. SSH

>Crux:
>Tmux provides features like moving applications to the background and managing your workspace in the terminal in the absence of a GUI