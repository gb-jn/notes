# Vim Notes

## Magic Wands and Shell Commands  

If you type ".!" at the command prompt, you can execute a shell command and vi/m will insert the output of the command into to the file your working on at the cursor postion.  In normal mode you can just type !! and it will put you into command mode with .! already there.  

You can write the code straight to a line, then send it to : by hitting !! when in normal mode. see bboost21 day10 44.40.  ie. type out code on line 1, then in normal mode press !! then you will be at the command prompt :.! and are able to send the code on line one to the stin of a program and line 1 will then get replaced with the output from stout of the program you sent it to.  

Can execute a shell command over a range by using  :range,range!command, ie :13,23!sort, ie 13,23!sort  

You can send an entire section(paragraph(denoted by the next blank line)) to the : by positioning your cursor at the start of the section, then press !}. ie put cursor at line 1 then press !} and you will be put into command mode with something like this .,.+22! (which translates to here(.) to(,) here(.) + 22 lines(+22) which you can then send to a program in shell with the !).  

!:(linenumber) will give you more control then !}, by setting the end line of the section. Ie !:22 gives you a command prompt like this :.,.+22!  

You can read in files by using the :r command, ie :r /somefile/foo.  You can also read in the output of a command, ie :r !ls.




### The Vi/m way  
 
Once you understand the VIM language, then you can easily memorize a plethora of operations. Use this to understand VIM's vocabulary:  

COUNT NUMERAL + TEXT OBJECT COMMAND + MOTION (or OPERATORS) "3das" will perform "delete around sentence 3 times"
So, if practical, you could place a numeral followed by... a command:  

d=delete  
y=yank  (into memory buffer to "put" later)  
c=change (delete then insert new text)  
w=write  
s=search  
r=read  

and then a motion:  

) = move cursor to end of sentence  
( = move cursor to beginning of prior sentence  
} = move cursor to the next paragraph  
{ = move cursor to the beginning of the prior paragraph  
w = move cursor to next word  
b = move cursor back a word  
$ = move cursor to the end of the logical line  
0 = (zero) move cursor to the beginning of the logical line  
G = move cursor to the end of the file  
gg = move cursor to the beginning of the file  
h, j, k, or l (you might have to look those up)  

OR instead of a Motion, define a field of area using:  

a = around  
i = inside  

followed by the name of the area around the cursor:  

s = sentence  
p = paragraph  
w = word  
t = xml-tag <tag example>  lots of text between tags </tag example>  
< or > =  inside or around a tag, frequently found in xml documents  

### Some Vi/m command examples, Case Sensitive  
Command | Description  
--  |  --
:   |  Puts you onto the ex command line  
!   |  Execute external command  
:h  |  or :help to get help, ie :help something, get help for something  
:w  |  write  
:s  |  search  
:q  |  quit  
:q! |  force quit  
:r  |  read in a file, ie :r/tmp/foo will read in the contents of /tmp/foo into vi  
%   |  Move to matching paranthesis or bracket  
}   |  move cursor to the next paragraph  
{   |  move cursor to the beginning of the prior paragraph  
(   |  jumps to the beginning of the previous sentence  
)   |  jumps to the beginning of the next sentence  
/   |  Search, after search press n to find next, N to find previous  
a   |  Insert mode after current word  
A   |  Insert mode after current line  
C   |  change, capitol C will delete rest of the line and go into insert mode  
D   |  Deletes from cursor to the end of the line  
R   |  Redo  
d   |  means delete, it gets used on the next thing you input to it.  
d(  |  deletes from cursor to beginning of previous sentence  
d)  |  Deletes from cursor to the end of the line  
d)  |  deletes from cursor to beginning of next sentence  
das |  Delete around sentence(also deletes the whitespace around the sentence)  
dd  |  will delete the current line  
dis |  Delete inside sentence  
dj  |  will delete the current line and also the line below that line  
dk  |  will delete the current line and also the line above that line  
G   |  Move cursor to the end of the file  
i   |  Insert mode at current cursor position  
I   |  Insert mode at the beginning of the line  
gg  |  Move cursor to the beginning of the file  
o   |  Insert mode on next line(adds line)
O   |  Insert mode before current line(adds line)
p   |  pastes yank, will work across files  
R   |  go into replace mode  
y   |  seems to yank 2 lines  
yy  |  yanks the entire line  
y}  |  yanks paragraph  
yap |  yank around paragraph  
yas |  yank around sentence  
yaw |  yanks around word  
yip |  yank inside paragraph  
yis |  yank inside sentence  
yw  |  yanks from cursor to the end of the word  
y$  |  yanks from cursor to the end of the line  

## References  

https://linuxize.com/post/vim-find-replace/  
https://stackoverflow.com/a/66519897  
https://rwx.gg/tools/editors/vi/how/magic/  
https://rwx.gg/vimagic   
https://vim.rtorr.com/  

