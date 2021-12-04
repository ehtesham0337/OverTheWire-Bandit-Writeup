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

-Type ```ssh bandit6@bandit.labs.overthewire.org -p 2220```
- Enter the password  `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`
- Type `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`. 2>/dev/null takes stderr and throws it away!
- Then `cat /var/lib/dpkg/info/bandit7.password` and copy the password `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`
- Type `exit`

## **Bandit Level 7 → Level 8**
> The password for the next level is stored in the file data.txt next to the word millionth.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`
-Type ```ssh bandit7@bandit.labs.overthewire.org -p 2220```
- Enter the password  `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`
- Type `grep millionth data.txt`. You should see `millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV`. Copy the password.
- Type `exit`

## **Bandit Level 8 → Level 9**
> The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`

-Type ```ssh bandit8@bandit.labs.overthewire.org -p 2220```
- Enter the password  `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`
- Type `sort data.txt | uniq -u`. First the list will be sorted alphabetically, and then uniq -u prints only unique lines.
- Copy `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`
- Type `exit`

## **Bandit Level 9 → Level 10**
> The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Commands you may need to solve this level
`grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd`
-Type ```ssh bandit9@bandit.labs.overthewire.org -p 2220```
- Enter the password  `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`
- 
