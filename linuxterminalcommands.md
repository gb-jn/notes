# Unix and Linux Commands and Notes

## Some commands
Command    |  Description
--         |  --
""         |  double quotes can have $variables in them, it will print/echo whatever the variable has in it.  
\>         |  redirect and overwrite(clobber). Clobber can be set to off to prevent overwrite files accidently.
\<         |  File input redirect  ie bc < somemathfile.  
\>\|       |  force overwrite(assume useful if no clobber is set on)  
\>\>       |  redirect and add to the end of the file(append).  
\<\<       |  "Here" Document operator.  
$SHELL     |  Built in shell variable that outputs what shell is being used (echo $SHELL)  
$PWD       |  Present working directory, special variable in shell  
$PATH      |  path. special variable in shell, list everything in path  
${variable}|  I think writing a variable this way prevents globing?  
&          |  after a program call will put it in the background.  
''         |  Single quotes will print/echo literally whatever is between them, will print/echo literally the string '$variable'  
.          |  Dot. means this directory right here  
--help     |  Similar to man and info  
\          |  Escape a charactor. put this in front of a command to use the not aliased version. 
1          |  standard output. ie redirect to a file 1>somefile. You can leave the 1 off becuase it's so common to redirect standard output.   
2          |  Standard error. ie redirect standard error to a file by 2>afile.  
bc         |  starts calculator  
basename   |  strip directory and suffix from filenames.  Don't use it, use parameter expansion to strip the things, basename is not needed and will open up a subprocess to do it's thing when you don't need to.  
cal        |  shows the calender  
case       |  https://youtu.be/3kEBhmMnk6M?t=3651
cat        |  Prints to stout  
cd         |  change directories  
cd -       |  cd into the previous directory  
clear      |  clears the screen  
cp         |  Copies a file/directory  
ctrl-c     |  interupts what is currently happening, like breakline or something  
ctrl-d     |  sends I'm done giving you input?(use it to exit python interpreter for example)  
ctrl-q     |  un-suspends the terminal  
ctrl-s     |  suspends the terminal  
date       |  prints/echo date, time etc. can change what the output is ie. date -u +%Y%m%d%H%M%S to Get ISO Second
date con't |    date -d 'last week' to get exact time last week, see man date for more.  
echo       |  echo prints to the screen(stout) what argument you give it, it doesn't use standard input as an argument. Sidenote, echo -n is NOT POSIX, use printf. echo has an automatic new line.  
fg         |  brings backrounded process to the foreground  
fg         |  will bring backgrounded processes to the foreground
file       |  Tells the details about a file  
grep       |  get\|regular expression\|print  \^ is to search only the first charctor of a line.  
grep con't |  new grep line  
head       |  displays the lines at the top of a file  
htop       |  like top but different (Use to see all the running processes)  
info       |  similar to --help and man  
jobs       |  Shows all jobs
kill -l    |  Lists all interupt signals
less       |  not always installed, but is like more but better  
ln         |  Links stuff, \-s for a symbolic link  
ls         |  lists files and directories, user ls -1 to list everything one file per line  
man        |  man command to it command's manual  
man hier   |  to see the folder heirachy for linux 
mkdir      |  Makes a new directory, use -p to make nested directories  
mkfifo     |  Makes a FIFO pipe.  
mktemp     |  Create a temporary File or Directory  
more       |  pipe to more for easier to navigate outputs  
mv         |  Moves and/or renames files/directories  
nl         |  add numbered lines(ie. echo "yo" | nl will print 1 yo)  
nohup      |  no hang up, old school way to setup up a daemon
pgrep      |  process grep 
pkill      |  process kill
printf     |  prints stuff the standard out, no automatic new line  
ps         |  shows running processes  
pwd        |  present working directory  
read       |  Use read to read input, put -r to prevent backslashes, and -p is NOT POSIX  
reset      |  resets terminal if its broken in some way  
rev        |  reverse lines characterwise  
rm         |  Removes/deletes a file, |r to recursively delete, -f to force  
rmdir      |  Removes/deletes a directory safer(can't be forced), won't work if something is in the directory  
seq        |  prints a sequence of numbers out
set -e     |  This will stop a shell script from running if/when it throws an error  
set -o vi  |  Set vi mode for the command line  
set -x     |  adding this to a script will echo/print out each step of the shell script  
shopt      |  Short for Shell Options, print out current option settings if no arguments are given  
sort       |  Sorts lines, defaults to sort alphabetically. use -V to sort numerically    
stat       |  Tells exhaustive details about a file  
tac        |  Reverse version of cat  
tail       |  displays the lines at the bottom of a file  
tee        |  (tee somefile) writes to file and outputs to stout  
test       |  test file types and compare values  
top        |  Use top to see the running processes  
touch      |  updates timestamp of a file, will make an empty file if it doesn't already exist  
type       |  type tells you what thing will be executed from the path  
uniq       |  Finds unique lines  
visudo     |  edits the sudoers file  
watch      |  executes a program(command) fullscreen every 2 seconds 
wc         |  prints number of words, lines, charactors, and bytes in a file  
which      |  shows where a command file lives, NOT POSIX (shellcheck say use command -v)
who        |  tells you who is currently logged in, also when they logged in, and other stuff  
whoami     |  tells you who you are logged in as  
xargs      |  Build and execute command lines from standard input  



### Understanding ls -l Readout

ls -l blah  
-rw-r--r-- 1 root root 5 May 17 23:27 blah  
(- = d for directory, l for link, c for special charactor?? there are others)  
(rw- = permissions)(r-- = group permissions)(r-- = everybody else permissions)  
(1 = if ls -l on directory, how many things in the directory. On file how many files point to memory space?? to do with linking)    
(root = owned by) (root = group)    
(5 = how many bytes)  
(May 17 23:27 = time last modified)  
(blah = file name)    





### Special Terminal Escapes

Remember a terminal is just a teletype emulator  

Command | Description  
-- | --  
ctrl c  |  Sends an interupt signal (Does not do a 'Copy')  
ctrl [  |  Same as hitting Esc key  
ctrl s  |  Suspends the terminal, nothing will happen, all input will be put into a buffer  
ctrl q  |  Unsuspends the terminal and puts everything in the buffer into the terminal  
ctrl z  |  Sends current process to background (Does not quit the program)  
ctrl d  |  Sends end of file. It means "end of transmission"  
ctrl v  |  Does nothing in shell  
ctrl x  |  Does nothing in shell  


## Ubuntu
### apt commands
Command  | Description
--       | --
apt update   |  Updates the package index  
apt list --upgradable  |  Lists all the packages that can be upgraded  
apt upgrade  |  Upgrades packages to their latest versions  

