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

## Level 5 to level 6
Find file with properties (human-readable, 1033 bytes in size, not executable) and displays its content 

Commands used : 
```
find ~ -type f -size  1033c ! -executable -exec cat {} \;
 ```

## Level 6 to level 7
Find file with properties (owned by user bandit7, owned by group bandit6, 33 bytes in size) and displays its content 

Commands used : 
```
find /  -type f -user bandit7 -group bandit6 -size 33c -exec cat {} \;
 ```

## Level 7 to level 8
Search for matching patterns in a file

Commands used : 
```
grep "millionth" data.txt 
 ```

## Level 8 to level 9
Search for line of text that occurs once

Commands used : 
```
sort data.txt | uniq -u
 ```

 ## Level 8 to level 9
Search for human-readable strings in a file

Commands used : 
```
strings data.txt
 ```