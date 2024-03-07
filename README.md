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

## Level 9 to level 10
Search for human-readable strings in a file

Commands used : 
```
strings data.txt
 ```

## Level 10 to level 11
Decode a file contains a base64 encoded data

Commands used : 
```
base64 -d data.txt
 ```

## Level 11 to level 12
Decode a file contains a ROT13 encoded data

Commands used : 
```
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
 ```
## Level 12 to level 13
Reverse a hex dump and decompress it multiple time

Commands used : 
```
<!-- Hexdump reversion -->
xxd -r data.txt reverse

<!-- Check the file type -->
file reverse

<!-- Change the file extension depending on the output -->
mv reverse reverse.gz

<!-- Decompress the file -->
gunzip reverse.gz
 ```

The file was compressed several times using this compression methods in order : gzip, bzip2 , gzip, tar , tar, bzip2 , tar , gzip

Notes :

|Compression|Decompression command|Extension|
| :-------- | :------- | :-------- |
|gzip|gunzip|.gz|
|bzip2|bunzip2|.bz2|
|tar|tar -xvf|.tar|

## Level 13 to level 14
Connect to the server using a private key.
```
ssh -i sshkey.private bandit14@localhost -p 2220
```

## Level 14 to level 15
Submitting text to specific port and getting response. 
```
echo "level14password" | nc localhost 30000
```

## Level 15 to level 16
Submitting text to specific port using SSL encryption and getting response. 
```
echo "level15password"  | openssl s_client -connect localhost:30001 -ign_eof 
```


## Level 16 to level 17
Scanning a range of ports to find out which of them have a server listening on them.

Submitting text to specific port using SSL encryption and getting response. 
```
nmap -p 31000-32000 localhost 
echo "level16password"  | openssl s_client -connect localhost:30001 -ign_eof
nano sshkey.private
chmod 600 sshkey.private 
ssh -i sshkey.private bandit17@localhost -p 2220
```