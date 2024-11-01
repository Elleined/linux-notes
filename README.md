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
  [commandArgument(s)]
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
- *pwd*: Returns your current directory.
- *cd*: Change directory.
  - *cd ..*: Go back.
  - cd /path*: Go to specified path.
- *which*: Returns the directory of the specified command.
  ```
  which ls
  returns /usr/bin/ls
  ```

### File and Directory Commands
- *cp*: Copy
- *mv*: Move

## Users Commands
- *whoami*: Returns the current user.
- *id*: See user details.
- *last*: Returns the users that logged in, in your machine.
- *su*: Switch user.
- *adduser*: Add user to your device.
  - Remember that when you create a user in linux it will create a user and a group based on your specified username.
- *userdel*: Delete a user
- *usermod: Stands for user modification.

## Group Commands
- *addgroup*: Create a group.
- *groupdel*: Delete a group.

## Group and User Commands
- Add user to the group
  ```
  usermod -aG <groupName> <userName>
  ```
- Remove user to the group
  ```
  gpasswrd <userName> <groupName>
  ```

## Network Commands
- *ip a*: Returns ip address.
- *ping*: Check connectivity to other device like server.
  - *ping <ip_address>*
  - *ping <domain_name>*

# Service Manager/ Master Daemon / systemd Commands
- *ps -aux*: Will list all daemon processes in your system. ps stands for process.
  
- *systemctl start <daemonName>*: Start the specified daemon.
  
- *systemctl stop <daemonName>*: Stop the specified daemon.
  
- *systemctl restart <daemonName>*: Restsrt the specified daemon.
  
- *systemctl reload<daemonName>*: Reload the specified daemon it will not restart the daemon it will just reload the daemon configurations.
  
- *systemctl enable <daemonName>*: Specified daemon will automatically start when your system boots.
  
- *systemctl disable <daemonName>*: Specified daemon will not automatically start when your systems boots.
  
- *systemctl status <daemonName>*: Check the status of specified daemon.

## Other commands
- *visudo*: Opens the sudoers file, sudoers file contains the users that can execute the sudo command.
- *alias*: Will create an alias to a command.
  ```
  alias <your_custom_command> = "<real_command>"

  alias al = "ls -al"
  ```

## Useful shortcut keys
- ctrl + a: Your cursor will go the beginning of the line.
  
- ctrl + u: Clear everything before your cursor.
- ctrl + k: Clear everything after your cursor.
- ctrl + y: Paste deleted content.

- ctrl + l: Clear screen
- !!: Double exclamation point will run the last executed command.
- tab + tab: Will help and list all possible commands that you can execute in your current command.

# Shell prompt meaning
- Example:
```
[<username>@localhost ~] $
```
- *~*: means the root directory of the current user  
- *$*: means logged in user is non-root user.  
- *#*: means logged in user is root user.  

# Linux File System
- */*: Is the root directory.
- */bin*: This is where most of the binaries (terminal commands) file are stored.
- */boot*: This is where all the required files to boot the Linux OS resides.
- */dev*: Stands for Devices. Contains device files to facilitates access to all attached devices in your device.
- */etc*: Configuration files are stored here.
- */home*: Each user directory are located here. except to the root user.
- */lib*: Shared library files that are required for system boot.
- */media*: External device are mounted here.
- */root*: This is where root user directory resides. Root user has own folder.
- */sbin*: This is where most of the root/ super user binaries (terminal commands) file are stored.
- */tmp*: Temporary files are stored here and will be deleted when device shutdown or restart.
- */usr*: Contains executables, libraries, man files, etc.
- */var*: This is where the log files, email in-boxes, web application related files, cron files, and more are stored.

###### Note: inside /usr there are also /bin and /sbin which is confusing because we already have that in / directory right. Just ignore it.

# What is Daemon
- Daemon word come from geek methology which is an entity that neither good or evil it is just an entity doing his job in the background so that everything works fine as expected hence linux developers called the background tasks or processes Daemon.

- Daemons is the processes/ background tasks/ background process that starts automatically by your system for you to use the applications/ services smoothly for example printing daemons and networking daemons they are running some background tasks/ processes for us to use them when needed. Basically it is a process that we usually don't care about.

- Just like in windows background tasks/ processes is called services in linux is it called Daemons.

- Just like in windows the Services UI where all the process is visible. unlike linux there are no UI for them we use commands only and nothing is diifferent between windows and linux about these concepts of background tasks and processes.

### How to spot a Daemon
- Daemon usually ends with a letter 'd' which stands for daemon for example the ssh daemon is called "sshd".

### How to work with Daemons.
- For us to manage or work with daemons we only allowed to talk with *master daemon/ service manager* or also called as "systemd" that is also a daemon. "systemd" is a first daemon to start when we boot our linux system and also responsible for starting other daemons which is called forking.

### Difference between Foreground process and Background process
- Background process is the processes that we dont see it is a daemon. Meanwhile the foreground process is the process that we can see in screen and can be interrupted anytime we want unlike background process we need to execute a command just to stop it.

### How to interact with Master Daemon or Service Manager
- To interact with *systemd* we use the command called "systemctl" which stands for "system control". commands for theses is in command section of this readme file.
  
# Philosophy
- Everything in Linux OS is a file.

# Definition of terms
- bash: Bourne Again Shell.
- sudo: Super User Do.
- apt: Advance Application Tool just like maven repository in java ,packagist in php, and npm in javascript.
- daemon: is same as and also called service, unit, background process, and background task
- master daemon: is same as and also called as service manager and systemd.
- grep: Stands for Global Regular Expression Print.
- curl: Client URL(Universal Resource Locator).

# SSH
## Securing SSH
- Change default port
- Disable username password authentication and use ssh ket instea
- Disable root login
- Set timeout interval: Set inactivity time-out to auto-disconnect SSH clients
- Set max authentication attempls: To prevent brute force attacks
- Set connection attempts: A rate limiting to prevent DDoS attackes
- Add login grace time: Set a time limit for  the user to enter authentication credentials.
- Remove other authentication method if not needed commonly the ssh key is the most used other methods are not used.
- Disable empty passwords
- Disable

### SSH Commands
- Test ssh config
```
sudo sshd -t
```

- List all ssh connected to your server
```
w
```

- Copy files via SSH
```
scp -r <source> <destination>

scp -r /home/sampleUser/test.txt remoteUser@remoteIpAddress:/home/remoteUser/test.txt
```

### Articles for more info
https://www.linkedin.com/pulse/fortify-your-ubuntu-server-beginners-guide-ssh-mads-akselsen-xrvoe
https://www.digitalocean.com/community/tutorials/how-to-harden-openssh-on-ubuntu-20-04
