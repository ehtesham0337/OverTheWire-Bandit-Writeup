# OverTheWire: Bandit
This is a writeup for the Bandit Wargame by OverTheWire from Level 1-15. There are a plethora of ways to do it, so keep exploring all the various methods. My host Operating System is Windows 10 and I'm using Ubuntu in a VirtualBox VM.
## **Bandit Level 0**
>  The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0     and   the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.  
  Commands you may need to solve this level `ssh ` 
  Helpful Reading Material Secure
  Shell (SSH) on Wikipedia.
  How to use SSH on wikiHow.
- Open Terminal
- Type  ```ssh bandit0@bandit.labs.overthewire.org -p 2220```
- Enter Password ```bandit0```

## **Bandit Level 0 → Level 1**
>The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for   a level, use SSH (on port 2220) to log into that level and continue the game. **Commands you may need to solve this level** `ls, cd, cat, file, du, find`
 - Type `ls`. You should see the `readme` file.
 - Type `cat readme`
 - Copy the password `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`
 - Type `exit`


## **Bandit Level 1 → Level 2**
> The password for the next level is stored in a file called - located in the home directory.
Commands you may need to solve this level
`ls, cd, cat, file, du, find`
 - Login to bandit 1. Type ```ssh bandit1@bandit.labs.overthewire.org -p 2220```
 - Enter the password  `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`
 - To read the `-` file, type `cat ./-`
 - Copy the password `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`
 - Type `exit`

## **Bandit Level 2 → Level 3**
> The password for the next level is stored in a file called spaces in this filename located in the home directory.
Commands you may need to solve this level
`ls, cd, cat, file, du, find`
 - Type ```ssh bandit2@bandit.labs.overthewire.org -p 2220```
 - Enter the password  `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`
 - To read the file with spaces in its name, type `cat 'spaces in this filename'`
 - Copy the password `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`
 - Type `exit`
 
## **Bandit Level 3 → Level 4**
> The password for the next level is stored in a hidden file in the inhere directory.
Commands you may need to solve this level
`ls, cd, cat, file, du, find`

- Type ```ssh bandit3@bandit.labs.overthewire.org -p 2220```
- Enter the password  `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`
- Type `cd inhere` to go into the directory and to view hidden files, type `ls -a`
- Type `cat .hidden` and copy the password `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`
- Type `exit`

## **Bandit Level 4 → Level 5**
> The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
Commands you may need to solve this level
`ls, cd, cat, file, du, find`

- Type ```ssh bandit4@bandit.labs.overthewire.org -p 2220```
- Enter the password  `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`
- Use `cd inhere` and then type `file ./file0*` to print file types. Here "*" is the wildcard character.
- You will see `./-file07: ASCII text`, use `cat < -file07`
- Copy password `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`
- Type `exit`


## **Bandit Level 5 → Level 6**
>The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
human-readable,
1033 bytes in size,
not executable.
Commands you may need to solve this level
`ls, cd, cat, file, du, find`

- Type ```ssh bandit5@bandit.labs.overthewire.org -p 2220```
- Enter the password  `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`
- Type `find . -type f -size 1033c ! -executable`
- Then `cat ./maybehere07/.file2` and copy the password `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`
- Type `exit`

## **Bandit Level 6 → Level 7**
> The password for the next level is stored somewhere on the server and has all of the following properties:
owned by user bandit7,
owned by group bandit6,
33 bytes in size.
Commands you may need to solve this level
`ls, cd, cat, file, du, find, grep`

- Type ```ssh bandit6@bandit.labs.overthewire.org -p 2220```
- Enter the password  `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`
- Type `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`. 2>/dev/null takes stderr and throws it away!
- Then `cat /var/lib/dpkg/info/bandit7.password` and copy the password `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`
- Type `exit`

## **Bandit Level 7 → Level 8**
> The password for the next level is stored in the file data.txt next to the word millionth.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`


- Type ```ssh bandit7@bandit.labs.overthewire.org -p 2220```
- Enter the password  `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`
- Type `grep millionth data.txt`. You should see `millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV`. Copy the password.
- Type `exit`

## **Bandit Level 8 → Level 9**
> The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

- Type ```ssh bandit8@bandit.labs.overthewire.org -p 2220```
- Enter the password  `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`
- Type `sort data.txt | uniq -u`. First the list will be sorted alphabetically, and then uniq -u prints only unique lines.
- Copy `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`
- Type `exit`

## **Bandit Level 9 → Level 10**
> The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`
- Type ```ssh bandit9@bandit.labs.overthewire.org -p 2220```
- Enter the password  `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`
- Type `strings data.txt | grep '=='`. If you look up the man page for `strings`, it says " print the strings of printable characters in files". You should see many strings in the terminal preceeded by several =, among them `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk` seems to be the password. Copy it.
- Type `exit`

## **Bandit Level 10 → Level 11**
> The password for the next level is stored in the file data.txt, which contains base64 encoded data.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

- Type ```ssh bandit10@bandit.labs.overthewire.org -p 2220```
- Enter the password  `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`
- Type `base64 --decode data.txt`. You should see `The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`. Copy it.
- Type `exit`


## **Bandit Level 11 → Level 12**
> The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

- Type ```ssh bandit11@bandit.labs.overthewire.org -p 2220```
- Enter the password  `IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`
- Type `tr '[a-z][A-Z]' '[n-za-m][N-ZA-M]' < data.txt`  OR `tr '[a-z][A-Z]' '[n-z][a-m][N-Z][A-M]' < data.txt`. 
- Transalate (tr) replaces all instances of first set of characters with the other ones as given. In this case, each letter is shifted 13 positions.
- The output should be `The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`. Copy it.
- Type `exit`

## **Bandit Level 12 → Level 13**
> The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!).
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file`

- Type ```ssh bandit12@bandit.labs.overthewire.org -p 2220```
- Enter the password  `5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`
- As mentioned in question make a new directory in /tmp, copy `data.txt` int the  new directory and rename the file. Here I didn't rename it.
- `cd` into your new dir.
- xxd program is used to make a hexdump or to do the reverse. Using flag -r convert hexdump into the binary. File `data.txt` is a hexdump and convert it into a binary file `data2` using command `xxd -r data.txt > data2`


- Using command `file data2` , we found that `data2` is a gzip compressed data.
- zcat is a program supplied with gzip and is used to decompress gzip compressed files.
- Enter `zcat data2 > data3` then, `file data3`


- We found that `data3` is a bzip2 compressed data.
- bzcat is a program supplied with bzip2 and is used to decompress bzip2 compressed files.
- After `bzcat data3 > data4` and `file data4`, we found that `data4` is a gzip compressed file. Use command `zcat data4 > data5` and then again `file data5`


- `data5` is a POSIX tar archive. tar program is used for archiving file and options 'x' is used to extract an archive, 'f' is used to specify name of the tar archive and 'v' is used for more detailed listing.
- Use `tar -xvf data5` OR `tar -x -f data5` and then using `ls`, you will see there is now a `data5.bin` file. Use `file data5.bin`. Again it's a tar archive.

- `tar -xvf data5.bin` outputs file `data6.bin` which is a bzip2 compressed file. Use `bzcat` to decompress it to `data7`.


- `data7` is a tar archive and use `tar` program which outputs `data8.bin`. data8.bin is a gzip compressed file and use `zcat` to decompress it to file `data9`.
- `data9` contains ASCII text and `cat data9` tells us the password

- `The password for the next level is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`. 
- Type `exit`




## **Bandit Level 13 → Level 14**
> The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on.
Commands you may need to solve this level
`ssh, telnet, nc, openssl, s_client, nmap`

- `ssh` into bandit13 with the password `8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`.
- There is a file called `sshkey.private`. Reading it gives us a RSA Key.
- Enter `ssh -i sshkey.private bandit14@localhost` and select `yes` to enter bandit14.


## **Bandit Level 14 → Level 15**
> The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
Commands you may need to solve this level`
ssh, telnet, nc, openssl, s_client, nmap`

- Use `cat /etc/bandit_pass/bandit14`, which could previously be only accessed by user bandit14, to get the current password `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`. Copy it.
- To submit it on localhost port 30000, use `telnet localhost 30000`.
- When it says 'Connected to localhost', enter `4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`.
- You will be greeted with `BfMYroe26WYalil77FoDi9qh59eK5xNr`, which is the password for bandit15.


