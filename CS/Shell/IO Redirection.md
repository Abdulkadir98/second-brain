There are 3 file descriptors in Linux
0 - STDIN
1 - STDOUT
2 - STDERR

These numbers maybe be placed before the redirection operator and there should be no space ebtween them

eg.
read X 0< /tmp/data

Reads the contents of data into the variable X

cat /etc/hosts 1> hosts
Writes the contents of /etc/hosts into a file named hosts

To redirect STDOUT to one file and STDERR to another file

eg. 
head -n1 /etc/hosts /fakefile > head.out 2> head.err
This will save the stdout in head.out and the stderr in head.err

To redirect both STDOUT and STDERR in the same file

head -n1 /etc/hosts > head.both 2>&1

Here the STDOUT is getting redirected to a file as usual but stderr is getting redirected to a file descriptor instead - when we want to use a file descriptor instead of a file precede the fd with an `&`. Now both STDERR and STDOUT get saved to head.both

Alternate syntax
head -n1 /etc/hosts /fakefile &> head.both