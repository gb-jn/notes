# RWXRob Beginner Boost 2021

See https://github.com/rwxrob/boost for the index and contents to the Boost(as at 2021 anyway)

## Day 7 Start using the Linux Terminal Command Line

> ### Outline from https://github.com/rwxrob/boost
> 
> ## <a id=day7> Day 7: Start Using the Linux Terminal Command Line
> [📺 Unedited Video](https://youtu.be/EBtWx5m7pds)
> 
> 1. The Command Line, Fastest Human-Computer Interface
> 1. Every Command Line Entered is a Line of Shell Code
> 1. Use Bash, Don't Play the Shell Game (For Now)
>    1. Interactive Shell is Not Same as Shell Scripting
>    1. Why Bash and Not Zsh, Fish, or Whatever?
>    1. Use Consistent Supported Bash Tab Completion
> 1. Understand the Parts of the Command Prompt
>    1. Username
>    1. Hostname
>    1. Interesting Origin of Email Addresses
>    1. Current Directory
>    1. Git Branch
>    1. Long Versus Short Prompts
> 1. Navigate Your Command History Efficiently
>    1. Use Up and Down Arrow Keys (For Now)
>    1. Use Initial Spaces to Stop Adding to History
>    1. Use Hashtag to Make One Line Comment Notes
>    1. Don't Learn More for Now (Learn `set -o vi` Later)
> 1. Send Special Terminal Escapes
>    1. Remember, a Terminal is Just a Teletype Emulator
>    1. `Ctrl-c` to Send Interrupt Signal (*Not* Copy)
>    1. `Ctrl-[` to Send Exact Same as `Esc` Key
>    1. `Ctrl-s`/`Ctrl-q` to Buffer and Suspend/Unsuspend
>       1. "Help! My Terminal is Frozen!"
>    1. `Ctrl-z` to Background Current Process (Not Quit)
>    1. `Ctrl-d` to Send EOF (End of File)
>    1. `Ctrl-v`, `Ctrl-x` Do Nothing (From Shell)
>    1. Silencing the Terminal Bell
> 1. Cut and Paste from Host Operating System
>    1. Depends on Terminal
>    1. First Ever Mouse Had Three-Button, Middle Was Paste
>    1. Windows Right Click to Paste
>    1. `Ctrl-x|c|v` Don't *Usually* Work (And Shouldn't)
> 1. Learn Useful and Essential Beginning User Commands
>    1. Use `reset` to Fix Bork Terminal
>    1. Use `clear` to Clear Screen (and Alternatives)
>    1. Use `watch` to Repeat Things and See Output
>    1. Use `man`/`help`/`info` Commands to Get Help
>    1. Use `less`/`more` for Paging Output
>    1. Use `ls` Command to List Files and Directories
>    1. Use `type` to See What Type of Thing It Is
>    1. Use `which` to See Where Command Lives
>    1. Use `pwd` Command to Show Working Directory
>    1. Use `cd` Command to Change Directories
>       1. Use `cd foo` to Change Into `foo` Child Directory
>       1. Use `cd ..` to Change Into Parent Directory
>       1. Use `cd -` to Toggle Change to Last Directory
>       1. Use `cd ~` (or Just `cd`) to Change to Home Directory
>       1. Don't Fall for Silly `cd` Replacements (Use `CDPATH`)
>    1. Use `cal` to View Calendar
>    1. Use `date` to View Dates and Times
>       1. Use `date -u +%Y%m%d%H%M%S` to Get ISO Second
>       1. Use `date -d 'last week'` to Exact Time Last Week
>    1. Use `bc` for Floating Point Precision Math Calculations
>       1. Don't Forget To Set Scale (`scale=2`)
>       1. Use Semicolons for Same Line
>    1. Use `top` to See Running Processes
>       1. Often Replaced with `htop`
---

### Notes for Day 7  

BOOK: The Linux Command Line - William Shots  
A lot of the linux command line stuff is covered in "The Linux Command Line - William Shots" book, but it uses bash shell scripting, we should learn POSIX shell scripting first.  
Worth reading the introduction.  
A lot of the websites refered to in the book have gone out of date.  
For most of the stuff we do, we will be using the POSIX tuturial website and the man page/s, and also a program called shellcheck(to check that our shell scripts are POSIX compliant.  
Skip the advanced keyboard trick section.  
Vi is better covered by rwxrob, he shows how to intergrate it with shell.  
Common task and essentials tools is outdated, doesn't cover any cloud native stuff.  
Networking will be covered in the boost.  
The regular expressions part in the book doesn't cover the topic properly. Regular expressions come in many different flavours, that's one of the reasons that perl was created.  Every (Programming)language has standardised on perl regular expressions. It's a big conversation, none of which is covered in the book, it just presents regelar expressions as is and doesn't cover the dangers of it all.  Refer to the regular expression part of the boost.  
Text processing part of the book is worth reading.  
Writing shell scripts can be skipped.  It is way too outdated, making the quality of the shell scripts it uses bad.  It refers to a way of serving webpages that wasn't even taken seriously back in the day(Something to do with cgi backend server processing).  Back in the day the backend of webpages was either done in either C or SHELL. Then perl took over, that's how it got famous, it was the number one thing for doing that kind of stuff.  Then python, php, etc came along, and that was the evolution of backend languages. rwxrob mentions all this because this section of the book was designed to teach someone shell scripting in 1997, in some sense that's great, but sometimes not so much.  Super dated, and all done in bash(who's days might be numbered, due to the gpl3 license. The main docker containers are running POSIX shells).  
Learn simple POSIX first before adding stuff onto it(like bash does).  Also learn vi without any addons before adding stuff on as well.  
TLDR: Read the first parts of the book, as mentioned.  Skip the shell scripting parts for now.  Come back to it after learning POSIX, if I want to see about it and it's bash ways.    
  
Every Command entered into the command line is a line of shell code.  

Use Bash as my interactive shell(Bash is standard for linux, also provides tab completion etc, In Bash shell I can't write a command and hit TAB twice to see what else I can do. Can't so that is base POSIX shell) until I know what I'm doing( the interactive shell is just an interpreter for shell code(commands are code)).  Use POSIX compliant code for writing shell scripts, they work everywhere.  

man dash and man sh to get help with shell.  

man git has great documentation for git.  
man gittutorial for a great tuturial on how to use git.  

In bc calculator don't forget to set the scale to get floating point math. ie scale=2, which means 2 decimal places.  


## Day 8 Install software from package manager  

> ### Outline from https://github.com/rwxrob/boost  
> 
> ## <a id=day8> Day 8: Install Software from Package Manager
> 
> [📺 Unedited Video](https://youtu.be/6EDT-Vc4PCY)
> 
> 1. Create and Name a Workspace Container
>    1. `docker run -it --name boost -h boost ubuntu`
>    1. Difference Between Detach and Exit
>       1. Detach with `Ctrl-pq`
>       1. Exit with `exit`
> 1. Understand Container States and Storage
> 1. Manage Software Packages from Command Line
>    1. Restoring Documentation and More with `unminimize`
>    1. Understand Linux Package Management
>    1. Use `apt update`
>    1. Use `apt search`
>    1. Use `apt install`
>    1. Use `apt remove`
> 
---  
### Notes for Day 8  

Nothing yet

## Day 9 Work with File System from Command Line  

> ### Outline from https://github.com/rwxrob/boost  
> 
> ## <a id=day9> Day 9: Work with File System from Command Line
> 
> [📺 Unedited Video](https://youtu.be/eZV14xpFAlA)
> 
> 1. [OverTheWire], Fun Hacker Practice
> 1. Understand the Linux File System
> 1. Use `mkdir` to Make a New Directory
> 1. Use `mktemp` to Make a New File or Directory
> 1. Use `rmdir` to Remove an Empty Directory
> 1. Use `touch` to Make a New File (or Update Timestamp)
> 1. Use `mv` to Move or Rename a File or Directory
> 1. Use `cp` to Copy a File or Directory
> 1. Use `rm` to Remove a File or Directory
> 1. Use `ln` to Link to a File or Directory
>    1. What is the difference between hard and soft link?
>    1. Used `ln` for Multicall Executables (BusyBox)
> 1. Use `file` to See What Details About File
> 1. Use `stat` to See Exhaustive Details About File
> 1. Use `cat` to Display Lines of a File, First to Last
> 1. Use `tac` to Display Lines of a File, Last to First
> 1. User `head` to Display Number of Lines at Top
> 1. User `tail` to Display Number of Lines at Bottom
> 1. Use `grep` to Find Lines of a File
> 1. Use `uniq` to Find Unique Lines
> 1. Use `sort` to Sort Lines
>    1. Use `wc` to Count Lines, Words, Bytes, and Runes
> 
> [OverTheWire]: <https://overthewire.org/wargames/bandit/>
---  
### Notes for day 9  

Nothing yet


## Day 10 Understand Pipes, Sockets, and Redirection

> ### Outline from https://github.com/rwxrob/boost  
> 
> ## <a id=day10> Day 10: Understand Streams, Pipes, and Redirection
> 
> [📺 Unedited Video](https://youtu.be/rhknj8h0zU8)
> 
> 1. Understand Standard Output and Error
>    1. Use `echo` and `printf` to Print Stuff
>       1. Difference Between `echo` and `printf`
>       1. Never Use `print` (for Printers)
>    1. Use `>` File Redirect Operator
>       1. Fix `find` Command Errors with Redirection 
>    1. Use `>>` File Append Operator
>    1. Use `>|` Force File Overwrite Operator
> 1. Understand Pipes and Pipeline
>    1. Use `|` Pipe Operator to Connect Out with In
>    1. Power of Pipelines and Shell Integration
>       1. Watch Ken Thompson Describe UNIX Pipes
>       1. Pipes are at the Core of UNIX Philosophy
>       1. Use Shell and Pipes from Within Applications
>    1. Transform and Filter Lines
>       1. Use `nl` to Number Lines
>       1. Use `rev` to Reverse Line
>       1. Use `tee` to Pipe *and* Redirect Lines
>       1. Use `echo` for Arguments and `cat` for Lines
>       1. Use `xargs` to Transform Lines Into Arguments
>       1. Use `cut` to Remove Stuff from Lines of Stream
>       1. Use `tr` to Translate Stuff in Lines of Stream
>       1. Use `sed` to Edit Lines of Stream (Streamed `ed`) (More Later)
>       1. Use `jq` to Select from JSON Input (More Later)
>       1. Use `yq` to Select from YAML Input (More Later)
> 1. Get Standard Input Into Your Programs
>    1. Input Most Useful After You Know How to Code
>    1. Use `<` File Input Redirect Operator
>       1. Always Use `<` Instead of `cat foo | ...`
>    1. Use `<<` Here Document Operator
>    1. Use `read` to Read Input
>       1. Combine `printf` and `read` to Create Prompts
>       1. Always Use `-r` and Understand Why
>       1. Use `for` or `while` with Read for Line Loops
>    1. Use `curl` to Read Input from Internet
>       1. Usually Combined with `jq` or `yq`
---  
### Notes for Day 10

Everything is a stream, everything is a stream of ones and zeros.  Understanding streams become such a big deal in C++ world that they created a C out and a C in stream, and you redirect the data to those streams.  There are three main streams, standard input, standard output, and standard error.  
Standard output goes to the screen by default, ie. `printf "something\n"`, will print "something" to the screen(the \n is for a line return, as printf doesn't do an automatic line return(echo does)).  
Standard error goes to the screen by default as well.  It can get jumbled up with the standard output, which can be problematic. ie. if you use find, the permissions denied errors get printed out with the output. One way you can fix this is to redirect the standard error to a file, `2> somefile`.  

The UNIX philosophy is to make something that does one thing well and intergrates well.  
Pipes and pipelines is how unix gets all the programs to intergrate with each other.  In rwxrobs opinion pipelines are the most powerful part of unix.  You can think of a pipe as the stream coming out of one program streams into the next program.  

You can use whatever comes out of the standard output and use it as a variable by using $() to surround it. ie for `i in $(grep '#' Notes_LinuxTerminalCommands.md | cut -d ' ' -f 3); do echo $i "you"; done`  

Never cat output into a program, it makes the process blind to its environment, see bboost day10 1.07.20. use `<` to send into a program, ie `bc < somemathfile`, not `cat somemathfile | bc`.  

Here variable, see bboost21 day10 1.12.00. You can make a here variable, do this, `cat << theend`(or any other string for it to look for), then the command prompt wil go to `> ` and you can type stuff in, then when you type `theend`(or whatever you chose), cat cats all the stuff you wrote.  It's call a here variable.  Has something to do with reading from standard input.  

Don't mix up Arguments, like what `echo` takes, and input, like what `cat` uses. see bboost21 day10 1.18.28.  

Can use `read` for interactive user input.  

There are some schools of thought on not ever prompting for interactive user input at all, because it blocks the unix philosophy of pipe lines, the script can't be put into a pipeline because it will slow the pipeline down, and now it can't be put into an automated session.  This has been a big enough issue that there has been a program called yes created and all it does is output y for yes(I assume this should be incorporated in pipelines getting blocked waiting for user input).  


## Day 11 Edit files with Vi(then Vim)

> ### Outline from https://github.com/rwxrob/boost
> 
> ## <a id=day11> Day 11: Edit Files with Basic Vi (Then Vim)
> 
> [📺 Unedited Video](https://youtu.be/RJ3EVB5-Emw)
> 
> *Please note that I mistakenly say `Ctrl-C` many times in this video
> where I actually mean `Ctrl-[`. See if you can catch all the times I get
> it wrong. It will be a good way to learn from my mistake.*
> 
> 1. Vi ("Visual Mode") History and Legacy
> 1. Why Vi/m and Not NeoVim/Emacs/Nano/VSCode?
> 1. Appreciate the Difference Between `vi` and `vim`
> 1. Restore `Esc` Key to Its Original Keyboard Home
> 1. Use `Ctrl-[` Instead of `Esc` Key (Never `Ctrl-x|z`)
> 1. Do the Vim Tutorial (`vimtutor`), But Beware
> 1. Other Recommended Learning Resources
>    1. <https://openvim.com>
>    1. <http://vimgenius.com> (no `s`)
>    1. Vim Adventures is Strongly Discouraged
> 1. Start with Defaults and *Zero* Configuration
>    1. Complex `.vimrc` is *Not* for Beginners
>    1. Customizing `.vimrc` Requires Scripting Skills
>    1. Eventually, Learn a Little Vimscript (Not Lua)
> 1. Avoid Vim Pane Splitting (Use TMUX Instead)
---
### Notes for Day 11

Avoid panes splitting, because it's better to just use a multiplexer.  
See vim notes for more(Including running shell scripts from within vim).  


## Day 12 Manage Users, Groups, and permissions

> ### Outline from https://github.com/rwxrob/boost
> 
> ## <a id=day12> Day 12: Manage Users, Groups, and Permissions 
> 
> [📺 Unedited Video](https://youtu.be/TNdI8fNvP5k)
> 
> 1. How Much User Stuff Do I Need to Know?
> 1. Create and Manage Users and Groups
>    1. Use `adduser` and `useradd` to Create User
>    1. Use `su - <user>` to "Login" as User
>    1. Use `deluser` and `userdel` to Delete User
>    1. Use `usermod` to Modify User Settings
>    1. Use `addgroup` and `groupadd` to Create Group 
>    1. Use `delgroup` and `groupdel` to Delete Group 
>    1. Use `groupmod` to Modify User Settings
>    1. Use `passwd` to Change Passwords
>    1. Know the Files Involved
>       1. `/etc/passwd`
>       1. `/etc/shadow`
>       1. `/etc/group`
>    1. Use `id` to Get the User and Group Information
>    1. Use `login` to Login
>       1. Does Not Register as Logged in User
>    1. Use `su - <user>` to Simulate a Login as Root
>    1. Understand `root` Access
>       1. Use `sudo` to Grant `root` (SuperUser) Access
>       1. Use `sudo su -` to Get Root Shell
>       1. use `doas -s` to Do Something As Root
>    1. Use `who`,`w`,`whoami`,`who am i`,`last` to See Users
> 1. Understand UNIX File and Directory Ownership and Permissions
>    1. Use `ls -l` to See Permissions
>    1. Use `stat` to See Even More About File
>    1. Read, Write, and Execute Permission
>       1. On Files
>       1. On Directories
> 1. Modify Ownership and Permissions
>    1. Use `chmod` to Change Permissions
>    1. Use `chown` to Change Owner (and Group)
>    1. Use `chgrp` to Change Group
> 1. Know About Setuid, Setgid, and Such, But Don't Use 
---
### Notes for the day  

How much user stuff do i need to know?  

As a beginner if I'm getting into coding and basic system admininstration, I should know how to create a new user, remove a user, modify a user, change a users permissions, and check what users are on the system.  These things are what would fall under basic system administration, in the old days that's what it would be called.  

Create and Manage Users and Groups  

There are two commands to add users, one has been around since the seventies(useradd, which POSIX). The other one came about because of Debian(adduser), to make it easier to add a user.  

`adduser somename` is the easier command(ie adduser user2). It will do everything for you, it picks the id for you, it asks you what password you want to use. The adduser command has a built in perl script that was designed to set up schools and such, so it will ask you for a name, room number, work phone, home phone, and other. You don't have to put anything in there, if you don't want to.  

To change into the user you can user `su - somename` to switch to them(ie `su - user2`).  When you change into being the user from being root, you will no longer have permission to change any system files etc(root privileges).  If you need root access to do something, you can use the `sudo command` to do it(ie `sudo somecommand`).  

`useradd somename` is the old command to add a user to the system(ie `useradd another`).  It won't automatically create the users home directoy, and it will make the users shell /bin/sh. It also won't prompt for creating a password.  

To see all the user on the system.
`grep home /etc/passwd`    

If the user was made with adduser then it will look similar to this  
`user2:x:1000:1000:,,,:/home/user2:/bin/bash`  

or if with useradd like this  
`another:x:1001:1001::/home/another:/bin/sh`  

The parts to the user stuff are delimited by `:`.  The first part is the user name(user2, another), the next part(x) represents the user password(stored elsewhere on the system), the next part is the user id(1000,1001), the next part is the group id(1000,1001), the next part is the part(for adduser it's ,,,) if where all the school system set up is stored if you entered any(each bit of this information is separated by commas), the next part(/home/user2, /home/another) is the users home directory(remember useradd won't automatically create the folder, it will just point to it, you can use the -m flag when creating the user to have it create the home folder for you), and the last part(/bin/bash, /bin/sh) is the users shell.  

User home directory template can be made in /etc/skel, whatever is in the /etc/skel folder will be copied into the new user home directory.  
 
You can change the user settings, with usermod.  to change shell it would be, `usermod -s /bin/bash`, for example.  check man usermod for all the flags.  

To add a user to a group use usermod, ie `usermod -aG sudo user`.   

To see all the groups and what users are in them, `cat /etc/group`  

You can change ownership of something by using `chown`.  
`chown -R another:another another` will change the owner and the group of another to another(same as doing `chown -R another another; chgrp -R another another`)(the -R means recursive, it will change the directory and everything in it, be careful).  see bboost21 day12 28.55.  

Add the sudo group and add users to it to enable them to user the sudo command, which is a safer way for users to use root privileges.  

You can add users to groups with the addgroup and groupadd commands.  Also can use the usermod command.  

Groups can be deleted with the delgroup and groupdel commands.  

The user name is different to the ID. I think if you had a user "doris" and delete her, but not her files, then added her back, she will have a different ID, so isn't the owner of the files again. You need to change the new doris ID back to what it was.   

You can use the command ID (POSIX) to get user and group information.  

/etc/shadow has salted hashed passwords stored in it for all the users on the system(someone can take the hashed password and bruteforce crack it, with jack the ripper program or something), so keep it protected.  

the w command will show whos logged into the system.  

Understanding ls -l Readout
ls -l blah
-rw-r--r-- 1 root root 5 May 17 23:27 blah
(- = d for directory, l for link, c for special charactor?? there are others)
(rw- = permissions)(r-- = group permissions)(r-- = everybody else permissions)
(1 = if ls -l on directory, how many things in the directory. On file how many files point to memory space?? to do with linking)
(root = owned by) (root = group)
(5 = how many bytes)
(May 17 23:27 = time last modified)
(blah = file name)


Example code rwxrob wrote on fixing permission on the home directories for all user, taken from bboost21 day12 38.00.  https://youtu.be/TNdI8fNvP5k?t=2280 .  
```
for i in `ls -1 /home/`; do cmd="chown -R $i:$i $i"; echo "$cmd"; done
```
The most reliable way to change permissions is the non octal way(It's a big debate which way to do it).  
Permissions have a diferent meaning on a directory than they do on a file.  
Man chmod for more information on permissions.  
You can use 'chmod +x filename' to add executable permissions to "filename" (see bboost day 12 1.15.30)
symbolic links by nature appear to have full permissions, they actaully take on the permissions of the file it's linking to.  

On a multi user systems, the defualt permissions are to permisive, ie users can see each others home directories.  It too easy to hack across user accounts.  

Using `=` when setting permissions can be dangerous, it will set exact and making a mistake is too easy.  Use `+-` to change the permissions.  

Side note, don't put passwords in scripts(Sometimes the scripts is still readable by another account, even is it's not runable(it's better to encrypt it in some way, ie by using pass), ie permissions are set to read but not executable).  

stat gives the full life story of a file.  

Don't rely on security by obscurity.  

There is a difference with permissions between files and folders.  

Know that setuid, setgid, and such(overthewire has levels on these, if i want to learn them more) but don't use them.  what setuid does is it causes a program that's about to run, to run with the permissions of the owner of the program, instead of the user trying to run it.  

If I want to go into cyber security, it's important to have a really good understanding of everything rwxrob talked about at the end of this days boost.  


## Day 13 Scripts are just Terminal Commands in a File

> ### Outline from https://github.com/rwxrob/boost
> 
> 
> ## <a id=day13> Day 13: Scripts are Just Terminal Commands in a File
> 
> [📺 Unedited Video](https://youtu.be/72OmbZiyKsc)
> 
> 1. You're Already Coding, Every Command *is* Code
>    1. Commands are Really Just Functions with Arguments
> 1. POSIX Shell is a Universal Command Interpreter
>    1. Shell Started as Bourne Shell, Now Ash and Dash
>    1. Korn Shell Led to Bash and Zsh Interpreters
>    1. Awk, Perl, Python, Ruby, Node Also Shell Scripting
> 1. Create First Script 
>    1. Create a File Containing Some Commands
>    1. Know What *Interpreted* Means
>    1. Know What *Syntax* Means
>    1. Use `sh` Interpreter to Run Commands in File
>    1. Use `bash` Interpreter to Run Same Commands
>    1. Use `perl` to Attempt Same and Note Errors
>    1. Use `python3` to Attempt Same and Note Errors
>    1. Use `chmod +x` to Make File Executable
>    1. Add `#!/bin/sh` Shebang Line to Specify Interpreter
>       1. Even If Others Work, Use to Communicate to Others
>       1. Sets Vi/m Syntax So Suffix Not Needed
>    1. What's Up with `/usr/bin/env`?
>    1. Use `set -e` to Exit Program if *Anything* Fails
>    1. Use `set -x` When Needed for Debug Tracing
> 1. Difference Between *Running* and *Sourcing* Scripts
>    1. Use Dot (`.`) or `source` to Source a Script
>    1. Most Stuff Should Be in Script (Subprocesses)
>    1. Some Stuff Can't Be Done Any Other Way
>       1. Change Current Working Directory
>       1. Modify Current Environment
> 1. Put Executables in Your `PATH` to Run From Anywhere
>    1. Use `which` to See Which Executable Wins
>    1. Understand Difference Between `which` and `type`
>    1. Never Put `./` in Your Path
> 1. Manage Jobs and Processes
>    1. A Running Program is a *Process*
>    1. A Backgrounded Program a *Job*
>    1. `Ctrl-z` to Background Running Process
>    1. Use `jobs` to See All Background Processes
>    1. Use `fg` to Bring Background Job Forward
>    1. Use `&` and `nohup` to Start and Keep Program in Background
>    1. use `()` to Combine Into Single Process (Subshell)
>       1. Know `$$` Still Refers to Parent
>    1. Use `pgrep`, `pkill`, `kill`, `ps`, `/proc` to See Processes
>    1. Use `nice` to Change Priority of Process
>    1. Use `crontab` to Schedule Jobs in the Background
>       1. Editing Your `crontab` is Not Really Beginner
---
### Notes for the Day  

Every time you execute a shell command, you are coding.  

sh(and bash and others(python etc)) is an interpreter, it interpret the commands that we write and understand into machine language https://youtu.be/72OmbZiyKsc?t=1605 (truthfully speaking it converts them(commands) at the lowerst level to system calls, then the system calls are interpreted by the kermel,  and the kermel interprets the system calls into binary, and the binary goes straight to the device).  

What is syntax, grammar rules, the order of words in a sentence, how things go - in what order, requirements of the tokenizer(part of a compiler, or interpreter).  syntax is - the colon goes here, the period goes here, the semi-comma goes here etc.  

Using env in the shebang(#!) line is insecure. https://youtu.be/72OmbZiyKsc?t=2554  Although it is pretty standard across the board for poeple that are going to shared scripts.  If you're not sharing scripts, it is advised not to use this, as it's really insecure, it's slower(it takes a subprocess to do it).  It is a hack that the ruby community came up with in 2000 something, and it has just stuck, and now everybody does it.  Only user it if the script has a really broad audience, and it has to just work.  env opens up the thing whereever it is.  see rwxrob bboost21 day 13 45.00ish.  

A lot of the syntax for shell came from a programming language called algol, that's where we got the weird syntax from.  

You should learn POSIX shell first(it works everywhere), and get very good with it.  Then you can know very specifically what the differences between it and bash(standard on a lot of linux's), and understand why and what the differences are, and know what all the subtle differences are.  

In order for shell to run a script, it wants you to tell it the path to the script.  

don't put ./ in path. It opens you up to path exploits.  It will make a file/script executable from anywhere, common commands can be highjacked if you do this, see https://youtu.be/72OmbZiyKsc?t=4255 .  

shell $PATH, shell looks for executables in the path directories in order. The stuff in the front(top) wins.  This can be used for path exploits if you don't know what's up, ie if someone has put ./ in path and it's first up, then it can be used to nefariously, ie command highjack.  This is also a reason #!/usr/bin/env can be bad, it looks in your path(the safest way is to write an explicit full path to the interpreter you want, because the full path has to exist in order to get the program to run) so if i ran a script that had /usr/bin/env python, and someone had messed with my path to get there trojnaed python interpreter to run before the normal one, then ive been hacked. (Sidenote, check all download scripts before run them).  see https://youtu.be/72OmbZiyKsc?t=4477  .  

A program that is running is a process. A backgrounded running program is a job.  see https://youtu.be/72OmbZiyKsc?t=4925 .  

`nohup` is an ancient thing that is designed to allow you to log out of the machine and to put a job into the background and just let it run there. the only time that you would ever need to do that id if you wanted to run a program and have it run in the backgroung no matter what, even if you log out, if the machine is on it will keep running.  used for if you wanted to run a server or something, you might want to background that.  It's ancient, don't use it. see https://youtu.be/72OmbZiyKsc?t=5235 .  

`kill -l` will give all the signals that can be sent between programs/processes. see https://youtu.be/72OmbZiyKsc?t=5507 .  pgrep to search the running processes for something, ie pgrep -a perl.  see https://youtu.be/72OmbZiyKsc?t=5675 .  

Crontab. Crontab is something that allows you to schedule a jobs in the background to run at a certain time.  see https://youtu.be/72OmbZiyKsc?t=6078 . 


## Day 14 Start POSIX Shell Scripting, Functions

> ### Outline from https://github.com/rwxrob/boost
> 
> ## <a id=day14> Day 14: Functions, Procedures, Operations, Methods
> 
> [📺 Unedited Video](https://youtu.be/zRNwt1y3lr4)
> 
> 1. Get and Use `shellcheck` Throughout to Ensure POSIX
> 1. Know What *POSIX* Means [POSIX Standard]
> 1. Know What *Script* Means
> 1. Know What *Program* and *Programming* Mean
> 1. A Universe of Stateful, Composable Objects with Actions, Interacting
>    1. Not Specifically Talking About OOP, Much Bigger
> 1. On Programming Humans ...
>    1. Routines, Procedures, and Commands in the Real World
>    1. What About *Algorithms*?
> 1. It All Started with Math, Know Why Linear Algebra Matters
>    1. `f(x,y) = 3x + 2y + 3`
>       1. `x`,`y` are *Parameters*
>       1. `=`, `+` are *Operators*
>       1. `3x`, `2y`, `3` are *Operands*
>       1. Function Parameter Variables Receive Argument Values
>       1. "This functions *returns* the value ..."
>       1. Same in JS: `let z = (x,y) => 3*x + 2*y +3`
> 1. *True* Functions are *Not* Procedures
>    1. What About *Subroutines*?
>    1. What About *Methods*?
>    1. What About *Operations*?
>    1. What About *Commands*?
>    1. Even If Language Allows, Group Code Into Either
>    1. Know Advantages of One Over the Other
>    1. Know What *Functional Programming* Is
>    1. Know What *Side Effects* Are
> 1. Shell Functions Are *Not* Functions, They Are Subroutines
> 1. Use Action Verb When Naming
> 1. Use `foo() {}` to Create a Subroutine (Function)
> 
> [POSIX Standard]: <http://31.42.184.140/main/2328000/032a6956a51f4d1dd5c91aa161eee03a/IEEE%20%26%20The%20Open%20Group%20-%20IEEE%20Std%201003.1-2017%20%28aka%20POSIX%29%20%282017%29.pdf>
---
### Notes for the day  

Difference between arguments and parameters, https://youtu.be/mgeKcAPuK7c?t=344 .  Parametes are the name of the things that the argument is getting passed through, ie parameters would be height, width, length. the arguments would be 2, 5, 3 ie 2 high, 5 wide, 3 long.  

The difference between commands, functions, and procedures.  https://youtu.be/mgeKcAPuK7c?t=1596 .  The differenctiation between these things has been lost in todays world.  28:30 Pascal is a programming language that diferantiates between functions and procedures.  29:30 In object orientated programming, the term operation and method come up.  An operation is a procedure, or function, that doesn't necesarily specify how it's to be done.  That would be the method.  A procedure is a set of steps to follow, an algoryth is the guts of the procedure, the procedure is the name of the algorythm.  

29:55 (In javascript) The method that implements an operation can change. For example, ambulate, is an operation that both a person and a dog can do. They both can abulate, they can walk. But the way they can walk, the METHOD of their walking, is implimented through an entirely diferent routine.  

It's important to know the difference between functions and procedures. It makes for writing better code if I can keep it organised.  

Functions are self contained(and always returns a value), procedures go outside of it self to affect other things.  https://youtu.be/mgeKcAPuK7c?t=2400  

Always name starting with a verb(he doesn't really explain why, just says it's important. My guess is it helps describe what it's doing)  https://youtu.be/mgeKcAPuK7c?t=3159  

shell semi colons https://youtu.be/mgeKcAPuK7c?t=3263 .  

this, in shell scripts 
> #!/bin/sh
> say_hello() {
>    echo "Hello"
>    echo " How are you?"
> }

is the same as this
> #!/bin/sh
> say_hello () {
>    echo "Hello"; echo "How are you?"
> }

Shell just has subroutines/procedures, you can't make pure functions https://youtu.be/mgeKcAPuK7c?t=3456 . Shell is a simple language, it's mostly about grouping commands together and flow. So it doesn't really do things like returning values(like functions do), it can technically return a value but the value it return is either zero or some integer, the only reason it even does that is to tell you if the thing succeded or failed.  

Shell for the most part just uses strings(date type) https://youtu.be/mgeKcAPuK7c?t=4520 .  There are integers, but in order to write safe good shell code, the safer thing to do is to think of everything as a string.  


## Day 15 State, Data Types, Variables, and Constants  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day15> Day 15: State, Data Types, Variables, and Constants
> 
> [📺 Unedited Video](https://youtu.be/yHdUh6-qZw8)
> 
> 1. All Objects Have States: Mutable, Immutable, Persistent, Dynamic, Static
> 1. Variables Save Data as State
> 1. Types Declare How to View State Data
>    1. Same Data, Different Type
>    1. Binary (Base 2, Ones and Zeros, Digital)
>    1. Number 
>    1. Symbol or Letter
>    1. String
>    1. Bit Field 
>    1. POSIX Shell Only Has Strings and Integers
>    1. Use Strings for Everything
> 1. Function Parameter Variables Receive Argument Values
>    1. Like Putting Something Into Box or on List
> 1. Use `=` to Declare and Assign Variable
>    1. No Spaces Around Operator (`=`)
> 1. Use `$foo` to Use Variable After Assigned
> 1. *Always* Wrap with Double Quotes (`"$foo"`)
> 1. Use `"${foo}bar"` to Disambiguate
> 1. Don't Forget to Check with `shellcheck`
> 1. Use `bc` When Numbers and Math are Actually Needed
> 1. Understand *Scope* and Considerations
>    1. Know What *Scope* Means
>    1. Know What a *Block* Is
>    1. Know What *Global* Means
>    1. Know What *Local* Means
> 1. All Variables are Global in POSIX Shell


### Notes for the Day  

POSIX stands for Portable operating system interface.  

The best way to ensure that shell script is POSIX, is to run it through the shellckeck program.  

Put `set -e` at the start of scripts to make sure the script will stop if it throws an error, otherwise it will just keep on chugging through the script.  set -e will make the script act more like other languages, and it makes for safer code.  

Beware of the standard viminfo buffer not being big enough, need to put this into .vimrc `set viminfo='30,< 1000,s1000` https://youtu.be/yHdUh6-qZw8?t=764

Parameters are to arguments as variables are to values https://youtu.be/yHdUh6-qZw8?t=1299 .  

Always quote variables in shell, there's many cases where is doesn't matter but do it anyway. Here is an example of why, where `echo $hello` is echoing `"-e hello"` (ie, hello="-e hello")(or someone is trying to bash inject when hello=$1 or something like that, check the video)then it will allow interpretation of backslashes, so you must use echo "$hello" to stop that. see  https://youtu.be/yHdUh6-qZw8?t=1650 .  


Disambiguate variables with curly brackets {}. see https://youtu.be/yHdUh6-qZw8?t=2001 .  
example code for disambiguating a variable.  
> #!/bin/sh  
> 
> greeting="hello"  
> echo "${greeting}muchacos"  

Single quotes will print literally.  https://youtu.be/yHdUh6-qZw8?t=2093 .  
example code  
> #!/bin/sh  
> 
> greeting="hello"  
> echo '${greeting}muchacos'  

The above code that has single quotes around the echoed variable will print literally ${greeting}muchacos.  

In shell code, treat everything(arguments) as strings, even numbers. If I need to do math, pass the numbers(that have been treated as strings) to the program bc, and have it do the math. https://youtu.be/yHdUh6-qZw8?t=2521  .  Don't use shell to do math, it is not good, it will only do integer math, not worth it.  

The only data types shell code has is, strings, boolean, and integers(whole numbers, no floating point(decimal places)). There is no arrays, maps, hashes etc.  It is a simple language.  see https://youtu.be/yHdUh6-qZw8?t=2657 .  

The only variable that exist in POSIX shell is global variable assignment, there are no constants or anything like that.  see https://youtu.be/yHdUh6-qZw8?t=3955

The way you can debug your code `set -x` see [link](https://youtu.be/yHdUh6-qZw8?t=4746j) .  `set -x` will show every command as if it were executed from the command line.  So you can watch everything that is happening.  
 
You can't write truly functional programs in shell, because every variable is a global.  see https://youtu.be/yHdUh6-qZw8?t=5128 .  

## Day 16 Function and Command Communication  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day16> Day 16: Function and Command Communication
> 
> [📺 Unedited Video](https://youtu.be/Gv-39gfhKR8)
> 
> 1. *Calling* to Communicate
>    1. Know What to *Call* a Function or Subroutine Means
>    1. Arguments Contain Incoming Communication
>    1. Return Values Produce Outbound Communication
>    1. Calls Must Come After Declarations
> 1. Arguments Passed as Special Parameter Variables: `$1`, ...
>    1. No Parameters Between Parens `()`
>    1. Unlike Most Other Languages
> 1. Use `$0` to Get Name/Path of Executable Script
> 1. Use `$#` to Get the Total Number of Arguments Passed
> 1. Use `"$@"` for `"first" "second" "third"`
> 1. Use `"$*"` for `"first second third"`
> 1. Reminder About Necessity of Quoting (`"foo"`) Everything
> 1. Shell Functions Only Return Integers
>    1. Use `return [RVALUE]` to Set Return Value
>    1. Omitting `return` is Fine
>    1. Return Values are *Not* Output
>    1. Use `echo`/`printf` and `$(foo)` to "Return" Strings
> 1. Use `$?` for Last Return Value
> 1. Use `exit [RVALUE]` to Return Value for Program Itself
---

### Notes for the Day

Backticks will be replaced with the output of the command that's in them. see https://youtu.be/Gv-39gfhKR8?t=2418 .  Backticks are better suited to be used in the interactive shell than in scripts. If I want to use this type of thing in a script, it is better to use $() because then you can nest them.  see https://youtu.be/Gv-39gfhKR8?t=2468 .  

Every single argument in order thats getting passed into a shell functoin/procedure can be pulled with `$@`. see https://youtu.be/Gv-39gfhKR8?t=4230 .  ie main"$@" is the same as main "$1" "$2" "$3" ... etc 

There is a also `$*` which would be the same as main "$1 $2 $3". see https://youtu.be/Gv-39gfhKR8?t=4289 .  

Return values, a return of 0 in shell, means 0 errors happened. see https://youtu.be/Gv-39gfhKR8?t=4710 .  

Discussin on sub process tree,  see https://youtu.be/Gv-39gfhKR8?t=5035 .  

Creating fake return values in shell, see https://youtu.be/Gv-39gfhKR8?t=5727 .  


## Day 17 Flow, Conditions, and Logic

### Outline from https://github.com/rwxrob/boost

## <a id=day17> Day 17: Flow, Conditions, and Logic

[📺 Unedited Video](https://youtu.be/Nvsae1lVPwY)

> 1. Conditions Alter Flow
> 1. Use `test` to Check Condition (Read `test` Man Page)
>    1. Remember, `test` Not Needed for Single Command
> 1. Use `&&` and `||` to Create *Compound Conditions*
> 1. Use Range Notation (like `20 < i < 100`)
> 1. Know and Use *Short-Circuit Logic*
>    1. Use `test` to Keep it Clear to Read
>    1. Use `&&` to Join (Not `||`)
> 1. Use `set -e` to Assert Every Line or Exit
>    1. Use `|| true` to Make Assertion Optional
> 1. Avoid Problematic `[]` to Check Conditions
> 1. Use `if` to Group Commands If True
> 1. Avoid `else` Whenever Possible, Return Early Instead
> 1. Use `case` to Branch Multiple Conditions
---

### Notes for the Day

There are no arrays in POSIX shell, so you usually have to get around this by chopping up something else. see https://youtu.be/Nvsae1lVPwY?t=195 .  

You don't need to you else in your conditionals, see https://youtu.be/Nvsae1lVPwY?t=1254 .  

Premature optimisation is the root of all evil. It is more important to write understandable code.  see https://youtu.be/Nvsae1lVPwY?t=1843 .  

White clean code, not fancy chicken scratch that will take other people longer to decipher it. No need to flex mad coding skills, especially in production code.  

The test operator is the most important thing that we will learn when is comes to conditionals is POSIX shell.  

Double brackets are bash only. see https://youtu.be/Nvsae1lVPwY?t=2731 .  == is not POSIX either.  man test is your friend.  

Compound conditions are the 'and' and 'or' and stuff, when you have more than one thing in a row. see https://youtu.be/Nvsae1lVPwY?t=2731 .  

I need to learn everything about test, it is very important to understand. see  https://youtu.be/Nvsae1lVPwY?t=3695 .  

Example code  
> #!/bin/sh
> 
> if test $# -ne 1; then
>   echo "usage: has <path>" >&2
>   exit 1
> fi

The $# in the code above means "number of arguments being passed in". The >&2 means that it is to be echoed to sterr.  

At the end of the video is the discussion on using && instead of || in short circuit conditionals.


## Day 18 Loops, Signals, and Events

### Outline from https://github.com/rwxrob/boost

> ## <a id=day18> Day 18: Loops, Signals, and Events
>
> 1. Power of Loops on the Command Line
>    1. Use `watch` for Simple Repetition
>    1. Iterating Over Ranges and Items
>    1. Creating Small Monitors and Services
> 1. Loops Repeat Commands Until Condition Met
>    1. Use `while` to Repeat While Condition True
>    1. Use `while true` for Infinite Loops
>    1. Use `sleep` to Lessen Impact to System
>    1. Use `until` to Repeat Until Condition True
>    1. Avoid Loops That Require Math in POSIX Shell
>       1. But If Needed, Remember, Integer Only
>    1. Understand "Init", "Check", "Change"
>       1. Arithmetic `for` Loops are Not POSIX
>       1. Can Be Done with `while` in POSIX
>    1. Use `for` to Repeat for Sequence or Number of Items
>       1. Use `seq` Instead of Bash `{1..10}` Notation
>    1. Use `break` to Break Out of Any Loop
>    1. Use `continue` to Start Next Iteration Early
> 1. Unexpected Benefits of Loops for Editing
> 1. Know What *Inter-Process Communication (IPC)* is and Methods
>    1. Signals are Just One IPC Method
> 1. Signals Communicate Between Programs
>    1. Use `kill`, `pkill` to Send a Signal
>       1. Use `Ctrl-C` from Within Process to Send Interrupt
>       1. Use `kill` to Send Terminate
>       1. Use `kill -1` to Send Hangup (Reread Config)
>       1. Use `kill -9` to Send Kill When Not Responding
>       1. No Need to Learn Others (For Now)
>    1. Use `trap` to Handle a Signal
> 1. Use Loops, `nohup`, and `&` to Create *Daemons*
>    1. Judicious Use of `&` Can Improve Concurrent Tasks
>    1. Better to Use `screen` or `tmux` (More Later)
> 1. Use `exec` to Exit a Program When Possible
>    1. Hands Off All Resources, Including Signal Handling
---

### Notes for the Day

56.32 need to know what the difference between var and let is.  

memorise kill -l it list all signals(related to ipc inter progam communication) see 1.06.16

systemd, the d stands for daemon. 1.10.00  

A process is just a running program.  The only difference between a processes that's ment to stay on forever and a daemon, is the daemon is set to ignore signals.  So that when you log out, it stays on, it's called nohup.  


## Dat 19 ANSI Escapes, Color, Gotchas, What's Next?

### Outline from https://github.com/rwxrob/boost

> ## <a id=day19> Day 19: ANSI Escapes, Color, Gotchas, What's Next?
> 
> 1. Happy Pride Month!
> 1. Don't Fear Color, All Modern Terminals Have Support
> 1. Know When to Use Color and When to Not
>    1. Use `test -t 1` to Detect Terminal Output
>    1. Use `reset` When You Break Your Interactive Terminal
> 1. Know What *ANSI Escapes* are, Which to Use, and How to Lookup
> 1. Use `printf` Because Escapes `\e` Properly
>    1. Avoid `echo -e` Which is Not POSIX
> 1. Prefer 16 Terminal Theme Colors for Compatibility
>    1. Use `\e[30m`-`\e[37m` for Terminal Theme Colors
>    1. Use `\e[1;30m`-`\e[1;38m` for "Bright/Bold" Variations
>    1. Add 10 for Background Colors
>    1. Use `\e[H\e[2J` to Clear the Screen
>    1. Use `\e[0m` to Reset Color
>    1. Avoid Dependencies from Sourcing Color Libraries
>       1. Write a [`termcolors`] Script, Run from Vim
> 1. Use Specific Colors When Needed
>    1. Understand These are *Never* Relative to Terminal Theme
>    1. Set `TERM` to `xterm-256colors` (or Whatever)
>    1. Use `\e[38;5;Nm` for "Hundreds" of Colors ( 0 <= N <= 255)
>    1. Use `\e[38;2;R;G;Bm` for "Millions" of Colors ( 0 <= R,G,B <= 255)
> 
> 1. Conclusion of POSIX Shell Scripting
>    1. What's Next for Shell Coding
>    1. Learn Bash `RANDOM` for Fun
>    1. Learn POSIX Parameter Expansion
>    1. You Just Don't Need `awk`, Ever
>    1. Sometimes You Need `sed` to Remain POSIX Compliant
>    1. Don't Use `expr`, It's Deprecated
>    1. POSIX -> Bash / Perl -> Python / CmdBox Go (Not Shell, But Still)
>    1. Learn Bash *After* Coding a Lot of POSIX First
>       1. Bash is Fine, When You Have It
>       1. Much Better Parameter Expansion
>       1. Safe Double Bracket Conditions
>       1. Regular Expression Support (Never Use `sed`)
>       1. Use `select` for Instant Interactive Menus
>       1. Read Google Bash Style Guidelines
>       1. It is Very Difficult to Keep Bashisms Out of Your Head
>    1. Node and Deno If You Must Have JavaScript
>    1. Ruby is Great as Well (If You Need It)
> 1. Some Fun Challenges to Get You Started
>    1. <https://rwx.gg/lang/cha>
> 1. Other Resources
> 
> [`termcolors`]: <https://raw.githubusercontent.com/rwxrob/dot/main/scripts/termcolors>
> 
> # Deal with Data, In a Structured Way
> 
> *Remember purpose of Boost is not to cover in depth, but to give a sense
> of what you need to know and why. Mastering these topics (SQL, for
> example) could take several months alone, writing your own language
> grammar in PEGN, a year or more*
---

### Notes for the Day  

Escape sequences are what give you colour and clear the screen and clear the line.  They are the standard for in-band signalling to control cursor location, color, font styling, and other options on terminals(from wikipedia).  

You can echo straight to the terminal an escape sequence.  

In order to use escapes, the terminal must support ncurses, all modern day terminals support ncurses.  

In order to use escapes with the echo command you have to use the -e flag.
Example  
```
echo -e "\n"
```
\n is the escape for a newline.  Which is not supported in POSIX. So it's better to use the printf command instead.  

Printf can use escapes and substitutions (%s).  
Example  
```
printf "%s\n%s\n" some thing
```
We can also add colours with printf.  

\e is an escape charactor, we can also put 033 which is the octal version. 

Non Posix way to get color in printf,  
```
printf "%s%s\n%s\n" $'\e[36m' some thing
```
It's believed that the escape sequences can't be substituded in, see https://youtu.be/VGbFGlUoa7I?t=1274 .  
I believe the POSIX way would be 
```
printf "\e[31m%s\n%s\n" some thing
```
More example code,  
```
for i in $(seq 30 37); do printf "\e[${i}m%s\n" Hello; done
``` 
You can add a 1; before the colour number to get the bold version of the colour, 
```
for i in $(seq 30 37); do printf "\e[1;${i}m%s\n" Hello; done
```   

If you break your terminal, use `reset` to reset the terminal(re initialize).  

You can clear the screen faster, for animation or something, by sending a clear screen sequence
```
\e[H\e[2J
```
The H is for clear screen and the 2J is to reposition the curso. I think. As opposed to runing the clear screen binary.  see https://youtu.be/VGbFGlUoa7I?t=1647 .  

To turn a colour off it is 
```
\e[0m.  
```

The escape sequence to use 256 colors is `\e[38;5;`    

To print out all the colours for 256 you can try this one liner:  
```
for i in $(seq 0 255); do printf "\e[38;5;${i}m%s\n" Hello; done  
```

The escape sequence to use rgb values is
```
\e[38;2;
```

An example of rgb is 
```
printf "\e[38;2;255;55;55m some \e[0m thing\n"
```

You can combine things, see https://youtu.be/VGbFGlUoa7I?t=2353.  

How to do a Blinking red 
```
printf "\e[5;31m some \e[0m thing \n"  
```

An explanation of the how the escape sequence is working to get the colours, the \e is the escape charactor that escapes the [ escape charactor for the terminal. see https://youtu.be/VGbFGlUoa7I?t=3090 .  

Parameter expansion. see https://youtu.be/VGbFGlUoa7I?t=4491 .  Man dash then search for parameter expansion, learn parameter expansion from dash to avoid learning non POSIX bashisms. 

There are two expansions that are primarily used.  One to cut off suffixes.  One to cut off preffixes.  

To cut off the preffixes use #.  To cut off suffixes ase %.  

Example  
```
path="/usr/bin/bash"; echo "${path#*/}"
```
In the above example, echo is echoing $path minus everything(denoted by using the \*) up to the first /(one # means up to the first occurrence)(Also, the / is what is being used as a delimiter is this case, although anything can be used). see https://youtu.be/VGbFGlUoa7I?t=4517 .  

If you want to go to the last /(The delimiter is the path is /, this is what we want to truncate to) then use two ##.  see https://youtu.be/VGbFGlUoa7I?t=4549 .  
Example  
```
path="/usr/bin/bash"; echo "${path##*/}"
```

To get rid of the suffixes do the same thing but with % instead.  
Example  
```
fullname="Rob Muhlestein"; echo "${fullname%% *}"
```
more example code
```
#!/bin/sh

# This code uses parameter expansion globbing to only accept the first word(name) if more than one is given.
printf "Hello, what's your name? "
read name
printf "Nice to meet you, %s.\n" ${name%% *}
```


## Day 20 Understand the need for Structured Data  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day20> Day 20: Understand the Need for Structured Data
> 
> 1. What is Data?
> 1. Evolution of Data Utilization
> 1. Delimited Data (WS, Tab, Bar, Paths, CSV)
> 1. Universal JSON, YAML, and JSON-Schema Data
> 1. Pattern Matching (Globbing, Globstar)
> 1. Regular Expressions (BRE, PCRE)
> 
> Other important structured data formats to know:
> 
> * gRPC and ProtoBuf
> * Hashicorp Configuration Language (HCL)
> * ABNF, EBNF, PEG, and PEGN Specification Languages
> * Structured Query Language (SQL)
> * Markdown
> * INI and TOML
> * HTML
> * XML
---

### Notes for the Day  

IFS means input field separaters. Normally set to space tab and newline.  See man dash for IFS.  


## Day 21 Delimited Data (Space, Tab, Bar, CSV, PATH)  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day21> Day 21: Delimited Data (Space, Tab, Bar, Paths, CSV)
> 
> 1. Describe Differences Between Delimited Data Formats
> 1. Name Common Applications and Uses of Delimited Data
> 1. Know the Different Forms of *White Space* 
> 1. Know the Difference Between `PATH` and File Path 
> 1. Use Parameter Expansion to Get Prefix and Suffix
> 1. Use `cut` To Get At Stuff In The Middle (But Careful, Not Greedy)
> 1. Use `awk` If You Really Want (But You Don't Need It)
> 1. Use `tr` or `sed` to Change the Delimiter or "Squeeze" (Spaces, etc.)
> 1. Understand Input Field Separator (IFS) (Maybe use `()`)
> 1. Understand the Problems with CSV (Not the Source Manager)
---

### Notes for the Day  

wc command counts words, it is delimited by whitespace.  

The different forms of whitespace are Space, Tab(\t), Line Feed(\n, which actually stands for newline but I think it is the same thing), Carriage Return(\r, I don't think this works much), formfeed(\f).  

Tidbit. Go language only allows tabs, python allows either tabs or spaces but has to be one or the other.  see https://youtu.be/XueMgR7Im40?t=768 .  

Whitespace can also be any ansi control charactor.  https://youtu.be/XueMgR7Im40?t=952 . 

Databases, logs, and Paths are common things that use delimited data.  see https://youtu.be/XueMgR7Im40?t=1266 .  

Tidbit.  Don't put backticks(``) in your shell code, it's bad practise. Use $() instead.  see https://youtu.be/XueMgR7Im40?t=1833 .  

Tidbit.  Type env into terminal will show all the environment variable that you can use in your code.  see https://youtu.be/XueMgR7Im40?t=1996 .  

Example code of using cut
```
echo "name rank serial-number" | cut -d" " -f 2
```

Cut is the most effictive way to get stuff from the middle.  see https://youtu.be/XueMgR7Im40?t=2409 .  

Tidbit. Using `getent` instead of grep to get passwd stuff. see https://youtu.be/XueMgR7Im40?t=2994 .  

Use `tr` to spueeze repeating charactors(or sed, or perl if it's available).  see https://youtu.be/XueMgR7Im40?t=3103 .  

Tidbit.  `for` loops usually split on spaces.  see https://youtu.be/XueMgR7Im40?t=3257 .  

Parentheses cause a subshell to happen.  see https://youtu.be/XueMgR7Im40?t=3536 .  It will cause a subshell to happen(although it will have the same process ID).  Also, every single line is a subshell.  see https://youtu.be/XueMgR7Im40?t=3606 .  You can use this to your advantage to set scope on variables in shell(like IFS).  

CSV(Comma Separated Value) is not straight forward.  see https://youtu.be/XueMgR7Im40?t=3895 .  

Design you data so you won't need to write a state machine to parse it(design the data so it splits easily).  see https://youtu.be/XueMgR7Im40?t=4334 .  


## Day 22 Universal JSON, YAML, JSON-Schema

### Outline from https://github.com/rwxrob/boost

## <a id=day22> Day 22: Universal JSON, YAML, JSON-Schema

> 1. What is JSON and Why Does it Matter?
>    1. JSON is for Parsing, Not People
>    1. "Should I Use JSON5?" HELL NO!
> 1. What is YAML and Why Does it Matter?
>    1. YAML is for People and Programming
> 1. Know the Definition of *Schema*
> 1. Know the Definition of *Domain Model*
> 1. Use `jq`/`yq` to Parse and Output JSON/YAML Data
>    1. Install `jq` with `sudo apt install jq`
>    1. Install `yq` However
>    1. Always Surround Query in Single Quotes
---  

### Notes for the Day  

The difference between JOSN and YAML.  YAML is a superset of JSON.   

JSON stands for JavaScript Object Notation.  

JSON will help you understand data types, in general.  see https://youtu.be/3addpYgC3CU?t=787 .  

JSON is the most important structured data format that I can learn, I can get anything through apis.  see https://youtu.be/3addpYgC3CU?t=1928 .  

JSON is for parsing, it's not for people(easily readable).  see https://youtu.be/3addpYgC3CU?t=2509 .  

JSON5 sucks, because it throws out all the stuff that makes JSON so fast at parsing.  see https://youtu.be/3addpYgC3CU?t=2528 .  

YAML is for people and programming.  see https://youtu.be/3addpYgC3CU?t=2867 .  

YAML is not as efficient as JSON for parsing because of the way that it is. see https://youtu.be/3addpYgC3CU?t=3243 .  

Need to learn JSON compatible YAML for the bboost.  see https://youtu.be/3addpYgC3CU?t=3409 .  

YAML is good for when you want to create structured data, that can then be used to render a web page, or a mailing list, or any number of things.  see https://youtu.be/3addpYgC3CU?t=3466 .  


## Day 23 Pattern Matching (Globbing, Globstar)  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day23> Day 23: Pattern Matching (Globbing, Globstar)
> 
> 1. Use `shopt` to Activate Pattern Matching in Bash Shell
> 1. Use `*` to Match Zero or More of Anything
> 1. Use `**/` to Descend Into All Directories as Well
> 1. Use `?` to Match Exactly One of Anything
> 1. Use `{foo,bar}` to Match `foo` or `bar`
> 1. Use `[a-c]` to Match `a`, `b`, or `c` (Like `{a,b,c}`)
> 1. Use `[^a-c]` Match *Anything But* `a`,`b`, or `c`
> 1. Use `[^.]*` to Match All Non-Hidden Files
> 1. Skip POSIX Character Classes (For Now)
> 1. Know the Limitations of Globbing
>    1. Glob on the Command Line, But Avoid in Scripts
>    1. Extended Globbing (`**`, etc.) is Not POSIX
>    1. Can Expand Past Maximum Command Line Length
>       1. Consider `find` Instead When Needed
>    1. Know When a Regex Is Better
> 1. Learning Resources
>    1. Use Globbing for Static Site Generator ([20210327130106])
> 
> [20210327130106]: <https://youtu.be/Efk2M77naFU>
---

### Notes for the Day  

Today is about matching and substituting text.  

Glob, globbing, globstar are like(the same as?) pattern matching.  

`ls *.md` would be a glob.  You can do `**/*.md` to fing everything beneath as well.  

Can check the man page for more info, man bash/dash.  see https://youtu.be/PUAFYaUSzIE?t=808 .  

Can use ? to match a charactor, ie ???? would mean find a thing with 4 charactor, or ?????.md would find 5 charactors with a .md.  see https://youtu.be/PUAFYaUSzIE?t=1074 .  

Globbing and Regular Expressions are completely different.  see https://youtu.be/PUAFYaUSzIE?t=1124 .  

Matching specific different things, ie `*.{md,txt}`.  see https://youtu.be/PUAFYaUSzIE?t=1511 .  

Another cool thing that can be done, touch `foo.{txt,md,html}`.  see https://youtu.be/PUAFYaUSzIE?t=1630 .  

Also, touch foo{1..10}.md.  see https://youtu.be/PUAFYaUSzIE?t=1638 .  

Probably want to avoid globbing in general in scripts.  see https://youtu.be/PUAFYaUSzIE?t=1694 .  

Globbing sets.  see https://youtu.be/PUAFYaUSzIE?t=1768 .  

Globbing not.  see https://youtu.be/PUAFYaUSzIE?t=1806 .  

An underscore _ in POSIX is considered to be alphanumeric.  see https://youtu.be/PUAFYaUSzIE?t=1988 .  

As far as known globs dont allow how many of a thing you want to match.  see https://youtu.be/PUAFYaUSzIE?t=2544 .  

To build a static site by globbing the files in the directory.  see https://youtu.be/Efk2M77naFU> .  

Tidbit.  Make sure you wrap echo's in double quotes(for globbing), that is particularly important.  It performs differently whether it has double or single quotes(single will echo literally, instead of allowing globs).  see https://youtu.be/PUAFYaUSzIE?t=3496 .  

It's better to not use globbing in scripts, becuase of the limitations of how much * can actually do.  see https://youtu.be/PUAFYaUSzIE?t=3589 .  

Don't over complicate globbing, as soon as it's getting complicated you need to move to regular expressions(regex).  see https://youtu.be/PUAFYaUSzIE?t=4459 .  


## Day 24 Match and Parse with Regular Expressions  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day24> Day 24: Regular Expressions (BRE, PCRE)
> 
> 1. Know What a *Regular Expression* (REGX) Is
> 1. Know Regex is for Matching *And* Parsing
> 1. Use `[[ =~ ]]` in Bash When Needed and Available
> 1. Use `sed` if You Must
>    1. Basic Regular Expressions (BRE) Only
>    1. Just Don't Clutter Brain with BRE
> 1. Use Perl Regex Whenever Possible
>    1. Perl Set the Standard for Modern Regex (PCRE)
>    1. Use `\s` to Match White Non-Whitespace Class
>    1. Use `\S` to Match White Whitespace Class
>    1. Often `\s` and `\S` is All That's Needed
>    1. Use `\w` for Word Character Class
>       1. Remember `_` is Considered AlphaNumeric
>    1. Use `\b` to Match Word Boundary
>    1. Use `\p{}` to Match Unicode Properties
>    1. Use `[]` to Match Non-Standard Classes
> 1. POSIX Character Classes Less Relevant in Unicode World
>    1. The `[:lower:]` is Not Same as `Ll`
> 1. Use Alternatives When Possible and Necessary
>    1. Parameter Expansion
>    1. Substring Matches
> 1. Know Advantages of Regex Over Other Parsing Methods
>    1. Powerful
>    1. Succinct
>    1. Universal
> 1. Know Limitations of Regex Versus Other Parsing Methods
>    1. Some Grammars Cannot Be Represented
>    1. Often Unnecessary Overhead
>       1. Cognitive
>       1. Technical
> 1. Learning Resources
>    1. <https://alf.nu/RegexGolf>
>    1. <https://regex101.com/>
>    1. <https://regexr.com>
>    1. <https://xkcd.com/1313>
---

### Notes for the Day  

The short difference between pattern matching(globbing) and regular expressions(regex), is that pattern matching(globbin) is mainly for matching patterns and regular expressions(regex) is for matching and replacing patterns.  see https://youtu.be/vCTg-EqKvEk?t=476 .  

When you say regular expressions to most poeple out there, they would think that you're going to validate and match something, parse it up and potentially replace it something else.  see https://youtu.be/vCTg-EqKvEk?t=493 .  

Replacement is a big part of regular expressions.  

In irc(and discord) you can use regex to replace something that you have commented. You can do `s/something/something else`.  https://youtu.be/vCTg-EqKvEk?t=555 .  

The number one reason to reach for bash instead of posix shell is to use double bracket regular expression potation( ie, `[[ =~ ]]` ).  see https://youtu.be/vCTg-EqKvEk?t=687 .  

Tidbit.  Perl allows you to deny all data until it's validated.  see https://youtu.be/vCTg-EqKvEk?t=1110 .  

Tidbit.  Don't use expr for anything, it has been deprecated for over a decade.  see https://youtu.be/vCTg-EqKvEk?t=1289 .  

sed uses BRE(Basic Regular Expressions) and BRE sucks(you can use non BRE but then it's not POSIX compliant, so no point. Just move to bash or perl).  see https://youtu.be/vCTg-EqKvEk?t=1396 .  But also maybe it is POSIX with -E(extended regular expressions).  see https://youtu.be/vCTg-EqKvEk?t=1678 .  

Don't use BRE or even learn them, just use perl or bash(they use the same pcre compatable regular expressions).  see https://youtu.be/vCTg-EqKvEk?t=1418 .  

Tidbit.  The best resource for PERL is the man page.  see https://youtu.be/vCTg-EqKvEk?t=2088 .  

Authors Note.  The best place I found to learn Perl regular expressions is https://perldoc.perl.org/perlretut .  


## Day 25 Don't Blow Up, Contain Your Customizations  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day25> Day 25: Don't Blow Up, Contain Your Customizations
> 
> [📺 Unedited Video](https://youtu.be/rTLGsG7cs6U?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Review Why Containers are Best for Learning
>    1. Shell Configurations are Riskier Than Most 
>    1. Explore and Experiment Without Fear
>    1. Don't Worry Amount Mounting Volumes (For Now)
>    1. Containers are Persistent (Until Deleted)
>    1. It's Perfectly Fine to Persist a Container While Learning
>    1. Eventually Push to GitHub as Backup
> 1. Start with a Fresh Ubuntu Container
>    1. Review Day [6](#day6),[7](#day7),[8](#day8)
> 1. Create a New User (See [Day 12](#day12))
> 1. Understand `/etc/skel` and Why It Matters
> 1. Understand What *Hidden* Means
> 1. Understand What *FreeDesktop* is About
>    1. <https://freedesktop.org>
>    1. Learn the [XDG Specification]
>    1. Use `~/.local/bin` Instead of `~/bin`
>    1. Use `~/.config/foo` Instead of `~/.foo`
> 
> [XDG Specification]: <https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html>
---

### Notes for the Day  

apt is a short form of apt-get. apt-get is preferred for non interactive mode.  

/etc/skel is like the template for new users home directory, everything in /etc/skel gets put into the home directory of a new user.  

Hidden simply means something that starts with a . (dot).  

FreeDesktop is an initiative that tells how to structure your files and directories, where to put them etc.  Instead of having stuff all over the place.  


## Day 26 Set Bash Options, Variables, and History Settings  

### Outline from https://github.com/rwxrob/boost

## <a id=day26> Day 26: Set Bash Options, Variables, and History Settings

> [📺 Unedited Video](https://youtu.be/3kEBhmMnk6M?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Connect to Your Saved Boost Container
>    1. `docker start -a boost`
> 1. Use `su - me` to Become Me (Or Whatever)
>    1. Know Difference Between `su` and `su -`
> 1. Install `vim`, `less`, `sudo`
> 1. Add `me` to `/etc/sudoers` with `visudo`
>    1. `me ALL=(ALL:ALL) NOPASSWD:ALL` (For Now)
> 1. *Never* Mess with Dotfiles from Installers
> 1. Don't Worry About `~/.bash_history` and `~/.viminfo`
> 1. Delete `~/.profile` (Not Used)
> 1. Delete `~/.bash_logout` (You Know Better)
> 1. Delete `~/.bashrc` (New One Coming)
> 1. Use `case` and `$-` to Detect Interactive Shell
> 1. Export `TERM`, `EDITOR`, `VISUAL` Variables
> 1. Export `TERM`, `EDITOR`, `VISUAL` Variables
> 1. Add `lessfile` / `lesspipe` Code
> 1. Add `HISTCONTROL`, `HISTSIZE`, `HISTFILESIZE`
> 1. Set `histappend` Shell Option
> 1. Set Vi History Editing Mode `set -o vi`
>    1. "Emacs" Mode is the Default (And Really Bad)
> 1. Add Your First Alias `alias c='printf "\e[H\e[2J"'`
---

### Notes for the Day  

There is a difference between  
```
su user
```
to change to a user, and 
```
su - user
```
to change to a user.  see https://youtu.be/3kEBhmMnk6M?t=817 .  

`su user` will log you into the user but not run as if you logged in as the user, so all your bashrc and vimrc stuff won't load in, for example.  

`su - user` will log you into the user as if you actually logged in as the user.  The `man su` page says that the `-` is shortcut for `--login`, and to use the preferred `--login` to avoid side effects caused by mixing environments.  

You can mess with your sudoers file with
```
visudo
```

The part of the video about .profile.  see https://youtu.be/3kEBhmMnk6M?t=1574 .  

Don't let install scripts screw with my PATH.  see https://youtu.be/3kEBhmMnk6M?t=3152 .  

Tidbit.  How to pretty print $PATH.  see https://youtu.be/3kEBhmMnk6M?t=3197 .  
```
echo -e "${PATH//:/\\n}"
```
Remember that `echo -e` isn't POSIX, the -e is to allow escapes.  Use the `printf` command to have escapes and remain POSIX.  

Tidbit.  You can turn of aliasing with `\`.  see https://youtu.be/3kEBhmMnk6M?t=3296 .  

Bash special parameter `$-` shows all bash flags.  `-` expands to the current option flags.  `$` expands to the process ID of the shell.  see https://youtu.be/3kEBhmMnk6M?t=3600 .  

Case, how to tell if a string is contained within another string.  see https://youtu.be/3kEBhmMnk6M?t=3651 .  

Export Environment Variables. You export environment variables so sub processes can access them.  see https://youtu.be/3kEBhmMnk6M?t=3846 .  


Bash shell options. You can man bash then search for the options(shopt) to see what you can do.  see https://youtu.be/3kEBhmMnk6M?t=4185 .  


## Day 27 Colorize Pager, Files, Directories (ls)  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day27> Day 27: Colorize Pager, Files, Directories (ls)
> 
> [📺 Unedited Video](https://youtu.be/a8zeMPEC0HA?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Reconnect to Your Boost Container
> 1. Add Terminal Escapes to Special Variables for `LESS`
>    1. Remember, Use `reset` if Your Terminal Messes Up
>    1. Do *Not* Use `MANPAGER` Color Method (Too New)
> 1. Add Directory Colors with `dircolor`
>    1. Use `command -v dircolors` to Check If Have It
>    1. Use `eval $(dircolors -b)` to set `LS_COLORS`
>    1. Set `alias ls='ls -h --color=auto'`
>    1. Add Custom `~/.config/ls/dircolors` 
>       1. Use `mkdir -p ~/.config/ls` to Make Directory
>       1. Get One From Net with `curl` (Install `curl` if Needed)
>    1. Use `test -r ~/.config/ls/dircolors` to Check for File
>    1. Use `eval $(dircolors -b ~/.config/ls/dircolors)`
>    1. Customise to Personal Style
---

### Notes for the Day  

Don't use manpager, it only works properly on arch linux.  see https://youtu.be/a8zeMPEC0HA?t=384 .  

The environment variables that we will be using to set the colours, are left over from days gone by. They will still be observed by less.  The are based on an old TERMCAP setting.  TERMCAP is the thing that was originally designed so that stuff would works with multiple different terminal types, but we just have XTERM terminal emulation across the board now, so we don't really need to worry to much about it now.  

Dircolors, sets the LS_COLORS. See man dircolors. Make a ~/.dircolors file to pull the colors from. System will use default colors if dircolors isn't used.  

If your terminal is all messed up, use reset to fix it.  

Need to have the .profile in home directory.  When bash starts up it runs .profile(unless .bash_profile or .bash_login exists).  .profile is used to run the .bashrc script when the shell start. It also sets up the user's bin's into path, if they exist.  


## Day 28 Customize Bash Shell Prompt  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day28> Beginner Boost, Day 28: Customize Bash Shell Prompt
> 
> [📺 Unedited Video](https://youtu.be/iR3zh3lau5g?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Reconnect to Your Boost Container
> 1. Just Say No to "Oh-My-Zsh" and Such
> 1. Understand the Science Behind Prompts
>    1. Older: Smaller Prompts Focus on What's Important
>    1. Newer: I Have Too Much to Communicate
>    1. Pay Attention, Don't Be Me (Story: Shutdown Company Mail Server)
> 1. Review What is Actually Useful to Have in Prompt
> 1. Build Up Gradually from Command Line First
> 1. Change `PS1` to Alter Prompt
>    1. Know Difference Between Single and Double Quotes
> 1. Read `man bash` (Use `/prompting` to Find)
> 1. Use `PROMPT_COMMAND` to Run Function for Each Command
> 1. Alter `PS1` from `PROMPT_COMMAND` Code for Creativity
> 1. Use ANSI Escapes for Color (See Day 19)
>    1. Use `\[`/`\]` to Keep Spacing Correct
---

### Notes for the Day  

PS1 is the main prompt, stands for prompt string 1.  

You can change the prompt colours with ansi escapes. ie

The prompt will stuff up if you don't put brackets [] in it. The reason is the \e[ escapes aren't being registered properly by the prompt internal machanism. The brackets [] have to be escaped as well, \[\].  see https://youtu.be/iR3zh3lau5g?t=1601 .  
Example
```
printf '\[\e[32m\]something\[\e[0m\] '
```

For all the things you can put in your prompt, do man bash then search for prompting.  

You can have parameter expansion in the prompt.  see https://youtu.be/iR3zh3lau5g?t=2086 .  

You can export the prompt so subshell can get it, you don't have to.  see https://youtu.be/iR3zh3lau5g?t=2388 .  

If you use double quotes for the prompt, it only gets evaluated once. So use single quotes so it gets evaluated every time it runs.  see https://youtu.be/iR3zh3lau5g?t=2658 .  

You can have a variable in the prompt.  see https://youtu.be/iR3zh3lau5g?t=2712 .  

You can make the prompt into a function by using PROMPT_COMMAND.  see https://youtu.be/iR3zh3lau5g?t=2802 .  


## Day 29 Use Aliases and Exported Bash Functions  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day29> Beginner Boost, Day 29: Use Aliases and Exported Bash Functions
> 
> [📺 Unedited Video](https://youtu.be/whlraJbk92E?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Know What an *Alias* Is
>    1. Use `alias` to Create Aliases
>    1. Affect Current Interactive Shell
>    1. Aliases Do *Not* Propagate to Subprocs
>    1. Aliases Cannot Be Exported
> 1. Know What an *Export Function* Is
>    1. Use `foo(){} && export -f foo` to Export Functions
>    1. Affect Current Interactive Shell
>    1. Functions Do *Not* Propagate to Subprocs Unless Exported
>    1. Exported Functions Affect Bash Subshells (Not Subprocs)
> 1. Use `shopt expand_aliases` to Ensure Active
> 1. Know When to Use a Alias vs Function
> 1. Know About "ShellShock" and How It Happened
> 1. Remember, Scripts are Almost Always Better
>    1. Except When Changing Current Interactive Shell
---

### Notes for the day  

The reason you put function in to the bashrc. It's because they get loaded into memory on shell initialization and are ready to go instantly.  They are very fast.  

The cdtemp script, didn't work as expected. Because it's creating a subprocess, then exiting out of the subprocess, puting you back to where you were.  see https://youtu.be/whlraJbk92E?t=1017 .  This is why you would make this kind of thing as an exported function in you bash script.  see https://youtu.be/whlraJbk92E?t=1098 .  

Export functoins, so subshells can use them.  see https://youtu.be/whlraJbk92E?t=1644 .  


## Day 30 Tab Completion and Sourcing  

### Outline from https://github.com/rwxrob/boost

> ## <a id=day30> Beginner Boost, Day 30: Tab Completion and Sourcing
> 
> [📺 Unedited Video](https://youtu.be/il6nnouiF34?list=PLrK9UeDMcQLre1yPasCnuKvWvyXKzmKhW)
> 
> 1. Know What *Tab Completion* Is
> 1. Use `<TAB>` to Page Through All Possible Commands 
>    1. Major Examples Include `git`, `pandoc`, `docker`, `kubectl`
> 1. Use `complete` to View All Completion Rules
> 1. Use `complete -C foo foo` to Build Completion Into Script
> 1. Copy Completion Rule to Make Shortcut (`docker` -> `d`)
> 1. Understand *Completion Mode* vs *Regular Mode* Execution
>    1. Check for `COMP_LINE` Environment Variable
>    1. Print Completion Possibilities One Per Line
>    1. Works for Any Language
> 1. Use Completion Helper Libraries When Possible
>    1. Shun Go `Cobra` as a Disease (14k Lines for `kubectl`)
>    1. Consider `compgen` to Create Complete Shell
>    1. Consider Go CmdTab (When Finished)
---

### Notes for the Day  

To read everything about programmable completion, go to man bash and search for programmable completion.  see https://youtu.be/il6nnouiF34?t=242 .  

You can use cd path to make it so you can cd into things that are not in the current directory.  see https://youtu.be/il6nnouiF34?t=425 .  

You can use `complete -C foo foo` to build completion into scripts(bash).  see https://youtu.be/il6nnouiF34?t=1111 .  
Example
```
complete -C foo foo
```

You may have to install completion onto your system first.  see https://youtu.be/il6nnouiF34?t=1266 .  

Don't forget you can type help complete.  

COMP_LINE. see https://youtu.be/il6nnouiF34?t=1729 .  

For more info on COMP_LINE, check the bash man page. 

NOTE: source is used the run lines out of a file into shell and execute them?

To source a file in POSIX use `.`  see https://youtu.be/il6nnouiF34?t=3331 .  

You can use `source` for non POSIX(ie bash).  see https://youtu.be/il6nnouiF34?t=3351 .  

More on sourcing  https://youtu.be/il6nnouiF34?t=3550 .  

Condider compgen(search man bash).  see https://youtu.be/il6nnouiF34?t=3684 .  


