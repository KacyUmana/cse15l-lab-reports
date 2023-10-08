# Lab Report 1
## `cd`
__Command with *no* arguments__

![Image](cd-no-arguments.png)

The command `cd` stands for "Change Directory," and its primary purpose is to change the current working directory within a shell or command prompt session. A working directory, also known as the current working directory (CWD), refers to the directory or current location in which a user is currently operating or executing commands. When the command `cd` is ran with no arguments, no error is produce nor is their any output in the terminal. This is because the `cd` command when used without arguments, defaults to switching the directory to the user's home directory. Your home directory is the directory associated with your user account, and it is where you start when you open a terminal. The behavior of the `cd` command without arguments is designed to provide a convenient way to return to your home directory.

__Command with a path to a *directory* argument__

![Image](cd-dir-arg.png)

When the command `cd` is used with a path to a working directory argument, no output nor error is produced in the terminal. However, the command will switch the current working directory to the path of the specificed work directory provided as the argument. In this case, the working directory that was run with the command was `/home/lecture1/messages`, so command `cd` changed my current working directory which was my home directory to the path of the lecture1/messages directory as specified. Directory paths can be specified as either absolute paths or relative paths (relative to the current directory). Absolute paths describe the full path from the root directory - starting point for all directory structures and absolute paths - of the file system to the target file or directory, regardless of the current working directory. While, relative paths specify the location of a file or directory in relation to the current working directory. Both absolute and relative paths work with command `cd` to change the current directory to a specified directory. 

__Command with a path to a *file* argument__

![Image](cd-file-arg.png)

When the command `cd` ia used with a path to a file as an argument, the terminal produces an output of a message that reads that the file path `/home/lecture1/messages/en-us.txt` is not a directory. The command is thus invalid and will result in the terminal to produce an error message. This is because the the primary purpose of the `cd` command is to change directories, not to access files. The command `cd` expects a directory as an argument, not a file. After receiving an error message, the current working directory will also remain unchanged because the file path specified in the argument is not used to change the working directory. In summary, using the `cd` command with a path to a file as an argument is not a valid use of the command, and will result in an error. cd is intended exclusively for changing the current working directory to a different directory, and it cannot be used for individual files. 


___


## `ls`
__Command with *no* arguments__

![Image](ls-no-arg.png)

Running the command `ls` with no arguments, the terminal produces a list of the contents of the current working directory. In this case the terminal produces the contents of the working directory. 

__Command with a path to a *directory* argument__ 

![Image](ls-dir-arg.png)

The command `ls` when ran with a path to a working directory as an argument, lists the contents of the specified directory. As seen above, the terminal output lists the content of the directory /home/lecture1/messages.

__Command with a path to a *file* argument__

![Image](ls-file-arg.png)

If you provide a file as an argument to ls, it will display information about that specific file, such as its name, size, and permissions (work on this shit)


___


## `cat`
__Command with *no* arguments__

![Image](cat-no-arg.png)

 Without any arguments, cat expects input from the user, so it waits for you to enter text. It's not commonly used in this way.

__Command with a path to a *directory* argument__

![Image](cat-dir-arg.png)

Using cat with a directory as an argument is not valid because cat is meant to display the contents of files, not directories.

__Command with a path to a *file* argument__

![Image](cat-file-arg.png)

This command will display the content of the specified file, /path/to/file.txt, in the terminal.
