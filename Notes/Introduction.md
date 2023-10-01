## What is a shell 
In the context of computing, a "shell" refers to a user interface that allows you to interact with an operating system or software application. It acts as an intermediary between the user and the underlying system, taking the commands you input and translating them into actions that the system can understand and execute. Shells are an essential part of the user experience on many computer systems.

There are several types of shells, but the two most common categories are:

1. **Command-Line Shells:**
   - **Bash (Bourne-Again Shell):** Bash is one of the most popular command-line shells in Unix-like operating systems (including Linux and macOS). It provides a powerful and feature-rich environment for running commands, scripting, and automation.
   - **Zsh (Z Shell):** Zsh is an extended version of Bash with additional features and customization options. It is known for its advanced auto-completion and theming capabilities.
   - **Fish:** Fish (Friendly Interactive Shell) is designed to be user-friendly and user-oriented. It offers intuitive auto-suggestions, syntax highlighting, and a rich set of built-in functions.
   - **tcsh and csh:** These shells are variants of the C Shell, known for their use in various Unix systems. They have features and syntax distinct from Bash.

2. **Graphical Shells:**
   - **Graphical User Interface (GUI) Shells:** These shells provide a graphical environment for interacting with an operating system. Examples include the Windows Shell in Microsoft Windows and the macOS Finder, which allow users to navigate files and folders using a mouse or touch input.
   - **Desktop Environments:** While not strictly shells, desktop environments like GNOME (used in many Linux distributions) and KDE provide a complete graphical user interface, including a shell, window manager, and various utilities to manage the desktop environment.

The choice of shell depends on personal preference, the operating system you're using, and the specific tasks you need to perform. Command-line shells are often favored by developers and system administrators for their scripting capabilities and efficiency in certain tasks, while graphical shells are typically used by everyday computer users for their ease of use and familiarity.

#### How to know which shell 
```
echo $SHELL
echo $0
```

## First script
```
#!/bin/bash
// to tell OS which shell is been used (not compulsory but recommended)

echo "Hello World!"
```
- make sure script has execute permission rwx
	- use command `chmod +x script.sh` to make it executable
- Run using 
	- ./script.sh
	- /path/script.sh
	- bash script.sh (using this not require making sh executable)
- Using `#`
	- `#this is comment`
- Multi-line comment
```
<<comment
...
your comment
...
comment

// example 
<<comment 
This 
is 
Multi
Line Comments
comment
```

### Variables
```
VAR_NAME=value
// here we are entering constant value

VAR_NAME=$(hostname)
// storing output of command

readonly VAR_NAME=value
// this put restriction on mistakelly changing the var value 

echo $VAR_NAME
```

### Arrays 
```

```
