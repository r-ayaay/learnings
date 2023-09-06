#vi #vim #cmd 

## vi mode commands:
k - move one line upwards
l - move one character to the right
h - move one character to the left
w,W - move one word to the right, past punctuation
b,B - move one word to the left, past punctuation
e - end of current word
1G - move beginning of file
ctrl+g - move to last line
ZZ - save and exit
x - delete char at cursor
X - delete char behind cursor
dd - delete line cursor is on
10dd - delete 10 lines following the cursor
yy - yank the current line (cut)
p - put yanked line below current line
P - put yanked line above the current line
## command mode commands:
:w - write out the file to save changes
:w filename - write the file to named file
:wq - save and exit vi
:w! - force save
:q! - dont save chnages and quit
:r filename - import a file into current file
:34 r filename - import file after line 34
:g/X/s/ /x/g Global search and replace (X=search, x=replace)

## input mode commands
o - add a new line after current line
O - insert a new line above current line