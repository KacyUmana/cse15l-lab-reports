# Lab Report 1
## `cd`
__Command with *no* arguments__

![Image](cd-no-arguments.png)

When the command `cd` is ran with no arguments, no output is produced in the terminal. The working directory is switched to the home directory. This is because the `cd` command when used without arguments, defaults to switches the directory to the user's home directory. There was no error in the output.

__Command with a path to a *directory* argument__

![Image](cd-directory-arg.png)

When the command `cd` is used with a work directory argument, no output is produced in the terminal. However, the command will switch the current working directory to the specificed work directory. In this case, the working directory that was run with the command was `/home/lecture1/messages`. There was no error in the output.

__Command with a path to a *file* argument__

![Image](cd-file-arg.png)

When the command `cd` ia used with a path to a file as an argument, the terminal produces an output of a message that reads that the file path `/home/lecture1/messages/en-us.txt` is not a directory. Attempting to change the current directory to a file will result in an error because the command `cd` is meant for directories, not files.

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

