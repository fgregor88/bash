# Navigation

## cd

## ls

## mkdir

# Streams and Piping

In Bash, running processes communicate through streams of text. When a command executes, the operating system automatically opens three standard data streams:

Stream	File Descriptor	Description
Standard Input (stdin)	0	The stream where a program reads its input data (defaults to the keyboard).
Standard Output (stdout)	1	The stream where a program writes its normal output data (defaults to the terminal display).
Standard Error (stderr)	2	The stream where a program writes error messages (also defaults to the terminal display, but is kept conceptually separate from stdout).
The true power of the shell comes from connecting these streams. The pipe operator (|) takes the stdout of the command on its left and directly feeds it as the stdin to the command on its right.

Command A | Command B

This mechanism allows you to chain small, single-purpose utilities into complex data processing pipelines without writing intermediate data to the disk.

To put this into practice, we can use a new utility called grep. It is a command-line tool used to search plain-text data sets for lines that match a regular expression or simple string.

If you are in a directory with hundreds of files and you want to use ls -la, but you only want to see the lines detailing files that contain the word "config", how would you construct the command using a pipe?
