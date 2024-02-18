# linux-notes
Notes for Linux Operating System

# Linux Distribution
- Since Linux OS is open source, many people modified it based on their specific requirements and release it with different name. Thus resulting to different versions of Linux OS is called Linux Distributions. So basically Linux distribution is just different version of Linux OS.

## Some popular linux distribution
- Ubuntu OS
- Kali Linux
- Red Hat
- Cent OS
- Open SUSE
- Debian
  
# Architecture
- **Hardware**: CPU, Motherboard, RAM, and etc...

- **Kernel**: Is the one capable talking to those hardware using drivers to execute binaries(0, 1) in hardware.
  
- **Shell**: Is the who will translate and take commands from the user that will be executed in kernel.
  
- **Commands**: A set of instructions (code) that will be created by the user to be executed in shell.
  
- **File Directory**: Is the one user will interact to.

# Commands
### Command Structure
```
command
  [-option(s)
    [optionArgument(s)]
  ]
  [argument(s)]
```

## Options
- Option that have double -- is the long version and options that has - single is the short version.
Example:
```
head -l // Short version
head --lines // Long version
```
- Some options have an required argument and other can be used without an argument.
Example:
```
ls -l // Option that has no required argument
head -n 20 // Option that has required argument 20 is the required argument.
```
### Combining multiple options
- We will use the short and long versions and commands to see the difference.
```
head --verbose --lines 20 // Long version

head -vn 20 // Short version
```

###### Note: It is important that you know the structure of command for you to read and understand what command will do and also it is important for you to know both the long and short version of options because if you dont know it sometimes its confusing as hell.

# Basic commands
- To see different options in the specific commands use.
Example:
```
ls --help
head --help
```

## File Commands
- *ls*: list all folder and files in current directory.
- *touch*: Created an empty file.
- *mkdir*: Create a folder.
- *rm*: Delete a file.
- *rmdir*: Delete only a empty folder.
- *cat*: Read a file.

## Directory Commands

# Definition of terms
- bash: Bourne Again Shell.
- sudo: Super User Do.
- apt: Advance Application Tool just like maven repository and packagist.
