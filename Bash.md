# Shells

A shell is a computing environment where commands can be interpreted, evaluated, and their output displayed. Shell commands can be difficult to learn, however a good shell provides access to a rich set of commands and allows simple programming of commands, which can be useful for creating powerful scripts and tools to improve your productivity as a software engineer. This tutorial provides a brief overview of bash shells. 

## Shell Basics

Bash (Bourne Again Shell) is a Unix shell command language that replaced the preceding Bourne shell in 1989. It has been the most popular interactive shell and is used as the default shell for most Linux distributions. If you would like to know more information about shells and learn additional commands, check out this thorough tutorial through [Software Carpentry](https://swcarpentry.github.io/shell-novice/index.html) for shell novices, [Command Line Fu](https://www.commandlinefu.com/commands/browse) or the [Unix Workbench](https://seankross.com/the-unix-workbench/) book. To access shells on your own:

* Linux: you already have a shell!
* Mac: you can run the Terminal in Applications and pin to your Dock.
* Windows: You access a shell in several ways. You can right click on the Windows Icon in the Task Bar and open a terminal window. You can also type in the name of the shell program in the search bar (e.g., Cmd/Powershell). To get bash on Windows, you will need to install an emulated shell with bash, such as Bash for Git or Windows Linux Subsystem (WSL).
> Tip: IDES, such as VS Code provide easy access to a terminal (View ⇨ Terminal).

### Commands

99% of the reason you use shells is to run useful commands.

##### Essential commands.

* **`ls`**: list content of a directory.
* **`cd`**: change directories to a new path.
* **`mkdir`**: make a new directory.
* **`pwd`**: output current directory
* **`cp`**: copy files
* **`rm`**: remove files
* **`touch`**: make a new empty file/update status
* **`echo`**: print out standard output
* **`cat`**: output the contents of a file
* **`head`**: output the first lines of a file
* **`tail`**: output the last lines of a file
* **`grep`**: search files for a key phrase
* **`wget`**: retrieve file from the web
* **`cut`**: extract output of a file (columns)
* **`awk`** and **`sed`**: Magic commands for extracting, searching, and transforming content

##### Combining commands

Command can run sequentially or conditionally:

```bash
command1 ; command2
(command1 ; command2) # in a sub-shell
command1 || command2  # do command2 only if command1 fails
command1 && command2  # do command2 only if command1 succeeds
```

##### Command I/O

The UNIX shell commands push data from sources through filters along pipes. Normally, each command runs as a process and reads and writes data the following way:

* **Standard input (stdin)**: get information from keyboard.
* **Standard output (stdout)**: write information as output to console.
* **Standard error (stderr)**: write error information as output to console.

Pipes and redirects change stdin and stdout from default sources. For example, we can change the stdin of a process to be piped from the output of another process. Or rather than printing to the console, we can get a process to write to a file.

```bash
command              # default standard in and standard out
command < inputFile  # redirect of inputFile contents to command as standard in
command > outputFile # redirect command output to outputFile as standard out
command >> outputFile # append the command output to the existing outputFile
command1 | command2  # pipes output of command1 as standard in to command2
```

Try the following scripts below to see some brief examples:

```bash|{type: 'command'}
pwd > path.txt && cat path.txt
```

```bash|{type: 'command'}
ls >> path.txt && cat path.txt
```

```bash|{type: 'command'}
echo "Hello World" > shells-test.txt && cat shells-test.txt
```

```bash|{type: 'command'}
grep "o" < shells-test.txt 
```

```bash|{type: 'command'}
echo "testing" | grep "o"
```

## Advanced: Setting Environment Variables

Bash commands are also very useful for setting up your environment. Think of [environment variables](https://ioflood.com/blog/bash-set-environment-variable/) as the settings of your Bash shell – allowing you to customize your shell environment, providing a versatile and handy tool for various tasks.

Setting an environment variable in Bash is straightforward. You use the `export` command followed by the variable name and its value like this: `export VARNAME="value"`.

Here's a simple example below:

```bash|{type: 'command'}
export USERNAME="<your_username>"
echo $USERNAME #prints out the value of the USERNAME variable
```

In Bash, an environment variable exists until it is explicitly removed with the `unset` command, or until the shell in which it was set exits. To permanently set an environment variable, you will need to add the `export` command in a login shell profile file (i.e., `~/.bash_profile` or `~/.profile`). We will do more with environment variables later in this workshop.

## Advanced: Shell Programming

Once you have a set of commands or steps you perform frequently enough, you might find it useful to put into a bash script, including:

* Data collection scripts for mining data; data processing and cleaning scripts.
* Set up a local server, vms or containers, or anything else needed to test or run a complex application.
* Provision and deploy an application on a remote server.

While you do these all in the context of a interactive shell, some of the following are particular useful for writing multiple lines of scripts. Bash scripts are usually created with a `#!/bin/bash` header at the top of the file and a `.sh` file extension. For example, create a `hello.sh` bash file to print out "Hello World":

```bash|{type:'file',path:'hello.sh'}
#!/bin/bash

echo "Hello World"

```

To execute a bash script, you can run:
```bash|{type:'command'}
bash hello.sh
```
or change the mode of the file to be an executable using `chmod` and run with `./`:
```bash|{type:'command'}
chmod a+x hello.sh ; ./hello.sh
```

Here are some other useful shell programming concepts:

```bash
# This is a Bash comment.

# If statement
if command; then
   commands
fi

# Error handling
[ -z "$var" ] && echo "var is undefined" || echo "var is defined"

# While loop
while command; do
  commands
done

# For loop
for (( i=10; i>0; i-- ))
do
    # Prints numbers counting down from 10
    echo "$i"
done

# Input/Output
read name # Get user input
echo "Hello $name!"
echo $1 # First command-line argument
echo $2 # Second command-line argument...

# Variables (storing values, results of commands, and referencing)
e=100
e=$(command)
$e
echo "result is: $e"

a=2                   # Integer.
let "a += 1"
echo "a = $a "           # a = 3
echo $a      
```
> ⚠️ Warning: In bash there are no types (everything is a character string) and spacing matters!

* Bash commands will reappear in the following notebooks. Please save the created files to provide with your workshop submission.

## [**Package Managers** ⏭️ ](Install.md)
