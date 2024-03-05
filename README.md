# the_bandit
Playing the bandit and keep track of the solutions

## Connection to the server 
Connected to the server using command :

`ssh username@hostname -p PORT`

`ssh bandit0@bandit.labs.overthewire.org -p 2220`

## Level 0 to level 1 
Displays the contents of a file

Command used : `cat readme`

## Level 1 to level 2 
Displays the content of a file with dashed name 

Command used : `cat ./-`

## Level 2 to level 3
Displays the content of a file with spaces in filename

Command used : `cat "spaces in this filename"`

## Level 3 to level 4
Displays the content of a hidden file 

Commands used : 
```
cd inhere
ls -a
cat .hidden
 ```

 ## Level 4 to level 5
Find human-readable file and displays its content (ASCII text)

Commands used : 
```
cd inhere
for FILE in *; do file ./$FILE; done
cat -file07
 ```