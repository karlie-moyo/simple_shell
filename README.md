# Simple Shell

![image](https://github.com/user-attachments/assets/ea8acbe9-f025-4f05-a7fc-67d5f456660e)

| PR.NO | PROJECT                                                                           | DESCRIPTION |
| ----- | --------------------------------------------------------------------------------- | ----------- |
|  0  | [Authors ](./AUTHORS/)                                                              | Karlie Moyo and Franklyn Tekenatei |
| 1   | [Builtins](./builtins.c/)                                                             | The code defines two functions for handling built-in shell commands: `builtins` checks and executes built-ins, and `check_builtin` verifies if a command matches a predefined list of built-ins like `exit` and `env`.   |
| 2  | [Builtins Header](./builtins.h/)                                                         | This header file declares functions for handling built-in shell commands, including builtins, check_builtin, bin_exit, bin_env, and bin_echo, along with helper functions for argument processing and printing.          |
| 3  | [Commands](./commands.c/)                                                                     | The analyze function processes command arguments by first checking if the command is a built-in, then verifying if the command has proper permissions or exists as a file, and finally attempting to execute it or locate it in the system's path, handling errors appropriately if the command cannot be found or executed. |
| 4  | [Commands Header](./commands.h/)                                                                 | This header file defines functions for handling commands in a shell program, including analyzing and executing commands, checking file permissions, working with environment variables, and managing the execution of built-in commands. It also includes the necessary headers for system-level functions like file handling and process management.           |
| 5  | [Env](./env.c/)                                                                  | The bin_env function is an implementation of the env built-in command in a shell program. It retrieves and displays the environment variables by calling the get_full_env() function, although it currently does not make use of the info and arguments parameters.    |
| 6  | [Environment](./environment.c/)                                                        | The code provides functions for retrieving environment variables, locating executable files in the system's PATH, checking if a path refers to the current directory, and printing all environment variables in the shell.    |
| 7 | [Error](./error.c/)                                                                | The code defines functions for handling and printing error messages based on specific error codes. It selects the appropriate error message, formats it with additional information like command numbers, and prints it, optionally including extra details when necessary. |
| 8 | [Error Header](./error.h/)                                                              | This header file defines the interface for error handling functions in a shell program. It includes functions for selecting error messages based on error codes (message_selector), printing general error messages (error), and printing errors with additional information (error_extra).  |
| 9 |  [Execute](./execute.c/)                                                                       | The file handles command execution in a separate process, managing errors, checking for executable permissions, and handling current directory commands within a shell environment. |
| 10 | [Exit](./exit.c/)                                                            |The file implements the exit builtin, which frees memory and exits the shell with the last status code, while also handling the validation of the exit argument. |
| 11 | [Free](./free.c/)                                                           |  This file defines two functions: free_memory_p to free a single pointer and free_memory_pp to free a double pointer by iterating through each element and freeing the memory.       |
| 12 | [General Header](./general.h/)                                        | This file defines macros, constants, and structures used for managing shell operations. It includes flags for interactive/non-interactive modes, error codes, and status codes, along with the general_t structure which holds various details about the shell session (e.g., arguments, command paths, error codes). Additionally, it defines structures for error handling (error_t) and built-in commands (builtin_t).    |
| 13| [Main](./main.c/)                                                                        | The main function is the entry point of the shell program. It initializes a general_t structure to store the shell's state, such as arguments and process ID. It checks if the shell is running in interactive mode by using isatty(STDIN). The start function is then called to begin executing commands. Afterward, the status code is returned, and the memory allocated for info is freed before the program exits.  |
| 14 |  [Main Header](./main.h/)                                                                    | The main.h header file defines the entry point of the shell program. It includes necessary libraries like stdio.h, stdlib.h, and unistd.h, and it declares the start function, which takes a general_t *info parameter. This function is responsible for initiating the shell's execution, and the file also includes the general.h header for the general_t structure. |
| 15 | [Man 1 Simple Shell](./man_1_simple_shell/)                                            | K-shell is a simple command-line interpreter for UoS School students, supporting interactive and non-interactive modes. It executes commands, handles basic environment variables, and provides error handling and signal management.|
| 16 | [Memory](./memory.c/)                                                            | The _realloc function reallocates memory by resizing an existing block. It handles four cases: if the new size equals the old size, if the pointer is NULL, if the new size is zero, or if it needs to copy data to a newly allocated memory block. It ensures efficient memory management by copying the data from the old block to the new one before freeing the old block. |
| 17 | [Memory Header](./memory.h/)                                                            | The memory.h file declares functions for memory management: _realloc for reallocating memory, free_memory_p to free a single pointer, and free_memory_pp to free a double pointer. |
| 18 | [Patterns](./patterns.c/)                                                              | The code processes and replaces patterns in strings by detecting $ symbols and replacing them with corresponding values. It includes functions to iterate through arguments, handle patterns, and reallocate memory to store the modified strings. |
| 19 | [Patterns Replacer](./patterns_replacer.c/)                                                   | The code provides functions for replacing special symbols in strings: replacement replaces $ and ? with the process ID and status code, respectively, and replace_env retrieves the value of an environment variable if it exists. |
| 20 | [Permissions](./permissions.c/)                                                               | The code defines two functions: is_executable checks if a file has execute permissions, and is_file verifies if a file exists and is executable. |
| 21 | [Printers](./printers.c/)                                                             |  This code defines two functions: _putchar_to_fd to print a single character to a specified file descriptor, and print_to_fd to print a string to a file descriptor, both returning the number of bytes printed or -1 on error.  |
| 22 | [Printers Err](./printers_err.c/)                                                        | The function print_err prints a message to standard error (STDERR) and returns the number of bytes printed. It utilizes the print_to_fd function for the actual printing. |
| 23 | [Printers Out](./printers_out.c/)                                                    | This code defines two functions: _putchar to print a character to STDOUT, and print to print a string to STDOUT, returning the number of bytes printed or -1 on error. |
| 24 | [Start](./start.c/)                                                        | The start function handles the shell mode (INTERACTIVE or NON_INTERACTIVE) and calls start_prompt to initiate the shell prompt.|
| 25 | [Test](./text.c/)                                                            | The code handles the shell prompt, reads user input, processes commands, and manages signal handling (e.g., SIGINT) to maintain interactive shell behavior.|
| 26 | [Test Header](./text.h/)                                                        | The header file defines functions and utility functions for managing shell prompts, handling strings, tokenizing input, printing output and errors, and replacing patterns like environment variables in a shell context. |
| 27 | [Tokenization](./tokenization.c/)                                                | The code contains two functions: split_words splits a string into words based on delimiters, while join_words concatenates three words with a separator and adds a newline. |
| 28 | [Utils Text](./utils_text.c/)                                                        | This code provides functions to manipulate strings: _strlen returns the length of a string, _strcat concatenates two strings, _strcpy copies one string to another, _strdup duplicates a string, and _strcmp compares two strings.|
| 29 | [Utils Text2](./utils_text2.c/)                                                            | This code provides utility functions for handling numbers and strings: digits counts the number of digits in a number, to_string converts an integer to a string, is_numerical checks if a character is a digit, _atoi converts a string to an integer, and contains_letter checks if a string contains any non-digit characters.|

    This is a collaboration project on Shell. We were tasked to create a simple shell that mimics the Bash shell. Our shell shall be called hsh

Project was completed using

    C language
    Shell
    Betty linter

General Requirement for project

    All files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
    All files should end with a new line
    A README.md file, at the root of the folder of the project is mandatory
    Use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
    Shell should not have any memory leaks
    No more than 5 functions per file
    All header files should be include guarded
    Write a README with the description of the project

Description

hsh is a simple UNIX command language interpreter that reads commands from either a file or standard input and executes them.
How hsh works

    Prints a prompt and waits for a command from the user
    Creates a child process in which the command is checked
    Checks for built-ins, aliases in the PATH, and local executable programs
    The child process is replaced by the command, which accepts arguments
    When the command is done, the program returns to the parent process and prints the prompt
    The program is ready to receive a new command
    To exit: press Ctrl-D or enter "exit" (with or without a status)
    Works also in non interactive mode

Compilation

gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh
Invocation

Usage: hsh [filename]

To invoke hsh, compile all .c files in the repository and run the resulting executable.

hsh can be invoked both interactively and non-interactively. If hsh is invoked with standard input not connected to a terminal, it reads and executes received commands in order.

Example:

$ echo "echo 'hello'" | ./hsh
'hello'
$

If hsh is invoked with standard input connected to a terminal (determined by isatty(3)), an interactive shell is opened. When executing interactively, hsh displays the prompt $ when it is ready to read a command.

Example:

$./hsh
$

Alternatively, if command line arguments are supplied upon invocation, hsh treats the first argument as a file from which to read commands. The supplied file should contain one command per line. hsh runs each of the commands contained in the file in order before exiting.

Example:

$ cat test
echo 'hello'
$ ./hsh test
'hello'
$

Environment

Upon invocation, hsh receives and copies the environment of the parent process in which it was executed. This environment is an array of name-value strings describing variables in the format NAME=VALUE. A few key environmental variables are:
HOME

The home directory of the current user and the default directory argument for the cd builtin command.

$ echo "echo $HOME" | ./hsh
/home/projects

PWD

The current working directory as set by the cd command.

$ echo "echo $PWD" | ./hsh
/home/projects/alx/simple_shell

OLDPWD

The previous working directory as set by the cd command.

$ echo "echo $OLDPWD" | ./hsh
/home/projects/alx/printf

PATH

A colon-separated list of directories in which the shell looks for commands. A null directory name in the path (represented by any of two adjacent colons, an initial colon, or a trailing colon) indicates the current directory.

$ echo "echo $PATH" | ./hsh
/home/projects/.cargo/bin:/home/projects/.local/bin:/home/projects/.rbenv/plugins/ruby-build/bin:/home/projects/.rbenv/shims:/home/projects/.rbenv/bin:/home/projects/.nvm/versions/node/v10.15.3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/projects/.cargo/bin:/home/projects/workflow:/home/projects/.local/bin

Command Execution

After receiving a command, hsh tokenizes it into words using " " as a delimiter. The first word is considered the command and all remaining words are considered arguments to that command. hsh then proceeds with the following actions:

    If the first character of the command is neither a slash (\) nor dot (.), the shell searches for it in the list of shell builtins. If there exists a builtin by that name, the builtin is invoked.
    If the first character of the command is none of a slash (\), dot (.), nor builtin, hsh searches each element of the PATH environmental variable for a directory containing an executable file by that name.
    If the first character of the command is a slash (\) or dot (.) or either of the above searches was successful, the shell executes the named program with any remaining given arguments in a separate execution environment.

Exit Status

hsh returns the exit status of the last command executed, with zero indicating success and non-zero indicating failure.

If a command is not found, the return status is 127; if a command is found but is not executable, the return status is 126.

All builtins return zero on success and one or two on incorrect usage (indicated by a corresponding error message).
Signals

While running in interactive mode, hsh ignores the keyboard input Ctrl+c. Alternatively, an input of end-of-file (Ctrl+d) will exit the program.

User hits Ctrl+d in the third line.

$ ./hsh
$ ^C
$ ^C
$

Variable Replacement

hsh interprets the $ character for variable replacement.
$ENV_VARIABLE

ENV_VARIABLE is substituted with its value.

Example:

$ echo "echo $PWD" | ./hsh
/home/projects/alx/simple_shell

$?

? is substitued with the return value of the last program executed.

Example:

$ echo "echo $?" | ./hsh
0

$$

The second $ is substitued with the current process ID.

Example:

$ echo "echo $$" | ./hsh
6494

Comments

hsh ignores all words and characters preceeded by a # character on a line.

Example:

$ echo "echo 'hello' #this will be ignored!" | ./hsh
'hello'

Operators

hsh specially interprets the following operator characters:
; - Command separator

Commands separated by a ; are executed sequentially.

Example:

$ echo "echo 'hello' ; echo 'world'" | ./hsh
'hello'
'world'

&& - AND logical operator

command1 && command2: command2 is executed if, and only if, command1 returns an exit status of zero.

Example:

$ echo "error! && echo 'hello'" | ./hsh
./hsh: 1: error!: not found
$ echo "echo 'all good' && echo 'hello'" | ./hsh
'all good'
'hello'

|| - OR logical operator

command1 || command2: command2 is executed if, and only if, command1 returns a non-zero exit status.

Example:

$ echo "error! || echo 'but still runs'" | ./hsh
./hsh: 1: error!: not found
'but still runs'

The operators && and || have equal precedence, followed by ;.
hsh Builtin Commands
cd

    Usage: cd [DIRECTORY]
    Changes the current directory of the process to DIRECTORY.
    If no argument is given, the command is interpreted as cd $HOME.
    If the argument - is given, the command is interpreted as cd $OLDPWD and the pathname of the new working directory is printed to standad output.
    If the argument, -- is given, the command is interpreted as cd $OLDPWD but the pathname of the new working directory is not printed.
    The environment variables PWD and OLDPWD are updated after a change of directory.

Example:

$ ./hsh
$ pwd
/home/projects/alx/simple_shell
$ cd ../
$ pwd
/home/projects/alx
$ cd -
$ pwd
/home/projects/alx/simple_shell

alias

    Usage: alias [NAME[='VALUE'] ...]
    Handles aliases.
    alias: Prints a list of all aliases, one per line, in the form NAME='VALUE'.
    alias NAME [NAME2 ...]: Prints the aliases NAME, NAME2, etc. one per line, in the form NAME='VALUE'.
    alias NAME='VALUE' [...]: Defines an alias for each NAME whose VALUE is given. If name is already an alias, its value is replaced with VALUE.

Example:

$ ./hsh
$ alias show=ls
$ show
AUTHORS            builtins_help_2.c  errors.c         linkedlist.c        shell.h       test
README.md          env_builtins.c     getline.c        locate.c            hsh
alias_builtins.c   environ.c          helper.c         main.c              split.c
builtin.c          err_msgs1.c        helpers_2.c      man_1_simple_shell  str_funcs1.c
builtins_help_1.c  err_msgs2.c        input_helpers.c  proc_file_comm.c    str_funcs2.c

exit

    Usage: exit [STATUS]
    Exits the shell.
    The STATUS argument is the integer used to exit the shell.
    If no argument is given, the command is interpreted as exit 0.

Example:

$ ./hsh
$ exit

env

    Usage: env
    Prints the current environment.

Example:

$ ./hsh
$ env
NVM_DIR=/home/projects/.nvm
...

setenv

    Usage: setenv [VARIABLE] [VALUE]
    Initializes a new environment variable, or modifies an existing one.
    Upon failure, prints a message to stderr.

Example:

$ ./hsh
$ setenv NAME Poppy
$ echo $NAME
Poppy

unsetenv

    Usage: unsetenv [VARIABLE]
    Removes an environmental variable.
    Upon failure, prints a message to stderr.

Example:

$ ./hsh
$ setenv NAME Poppy
$ unsetenv NAME
$ echo $NAME

$

What we learned:

    How a shell works and finds commands
    Creating, forking and working with processes
    Executing a program from another program
    Handling dynamic memory allocation in a large program
    Pair programming and team work
    Building a test suite to check our own code
    ### AUTHOR:
<details>
    <summary>Authors</summary>
    <ul>
        <li>
            <a href="https://github.com/karlie-moyo">Github</a>
        </li>
        <li>
            <a href="https://twitter.com/karlieemoyo">Twitter</a>
        </li>
        <li>
            <a href="https://karlieemoyo@gmail.com">e-mail</a>
        </li>
        <li>
            <a href="https://frankiperezi99@gmail.com">e-mail</a>
        </li>
    </ul>
</details>

---

### Acknowledgements  :pray:
___
All of the work in this project was conducted as part of the UoS-SE program's curriculum.
