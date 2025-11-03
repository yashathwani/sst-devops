# 02 nov notes

shell scripting class today. mostly about automating stuff in linux.

how to make a script:
1. create file with .sh (like test.sh)
2. put #!/bin/bash at the top (called shebang).
3. make it runable with chmod +x filename.sh.
4. run it with ./filename.sh.

variables:
- define it like NAME="yash" (no spaces!).
- use it with $NAME.
- read input from user with: read -p "what is your name: " VARname.

if and loops:
- use if [ condition ] to check things.
- -f checks if file exists.
- for and while loops to repeat stuff.

linux permissions & files:
- rwx = read, write, execute.
- chmod to change them.
- acls are for more detailed control than just basic chmod.
- basics: mkdir (make dir), cd (move), touch (new file), rm -rf (delete everything - be careful!).

text tools:
- tr, sed, awk to change text.
- to make things uppercase: echo $text | tr [a-z] [A-Z].
- find command: find <path> -name "thing" to search files.

functions:
- put code in a block to reuse it.
- write like: myfunc() { commands }.
- call it just by its name: myfunc.

user management:
- scripts can add users/groups using useradd and groupadd. sets up their home and shell etc.
