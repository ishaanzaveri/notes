# Bandit Walkthrough

This document will contain a walkthrough of the wargame `bandit`

## Level 0 - SSH

We use ssh to enter the machine.
`ssh -p 2220 bandit0@bandit.labs.overthewire.org`
`password: bandit0`

using `ls` we get the files
`cat readme` gives us the token
Password : `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

## Level 1

We use ssh again to enter the machine
`ssh -p 2220 bandit1@bandit.labs.overthewire.org`
password: `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

The file we are trying to open is a `-`
we cant simply do `cat -` because what that does is it refers to stdin/stdout

To read contents we can do `cat ./-` this yields the password: `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

## Level 2

We use ssh again to enter the machine
`ssh -p 2220 bandit2@bandit.labs.overthewire.org`
password: `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

the file that contains the passwords has spaces so we need to use `\` to escape the spaces

`cat spaces\ in\ this\ filename`
password: `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

## Level 3

We use ssh again to enter the machine
`ssh -p 2220 bandit3@bandit.labs.overthewire.org`
password: `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

The prompt says that the key is in a hidden file, so we use `ls -al`
It shows that there is a directory called `inhere`

so we `cd inhere` and then run `ls -al` to find the other hidden file.
the file is called `.hidden` and the password is `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

## Level 4

We use ssh again to enter the machine
`ssh -p 2220 bandit4@bandit.labs.overthewire.org`
password: `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

we `cd inhere` and then do `ls`

We get
`-file00 -file01 -file02 -file03 -file04 -file05 -file06 -file07 -file08 -file09`

to find out the file types we use the command `file`

```
bandit4@bandit:~/inhere$ file ./-file01
./-file01: data
bandit4@bandit:~/inhere$ file ./-file02
./-file02: data
bandit4@bandit:~/inhere$ file ./-file03
./-file03: data
bandit4@bandit:~/inhere$ file ./-file04
./-file04: data
bandit4@bandit:~/inhere$ file ./-file05
./-file05: data
bandit4@bandit:~/inhere$ file ./-file06
./-file06: data
bandit4@bandit:~/inhere$ file ./-file07
./-file07: ASCII text
```

we then cat `file07` and get the password : `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

## Level 5

We use ssh again to enter the machine
`ssh -p 2220 bandit5@bandit.labs.overthewire.org`
password: `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

we `cd inhere`

The prompt says the file we are finding is

- human-readable
- 1033 bytes in size
- not executable

Hence we can use `find -size 1033c ! -executable`
it gives us `./maybehere07/.file2` so we `cat ./maybehere07/.file2`

the password is `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

## Level 6

We use ssh again to enter the machine
`ssh -p 2220 bandit6@bandit.labs.overthewire.org`
password: `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

it says somewhere on the server with these properties

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

so I did `cd ../..` and `find -user bandit7 -group bandit6 -size 33c`
turns out `./var/lib/dpkg/info/bandit7.password` had the password

so we cat it ` cat ./var/lib/dpkg/info/bandit7.password`
password : `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

## Level 7

We use ssh again to enter the machine
`ssh -p 2220 bandit7@bandit.labs.overthewire.org`
password: `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

We use grep to find it `cat data.txt | grep millionth`
password: `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

## Level 8

We use ssh again to enter the machine
`ssh -p 2220 bandit8@bandit.labs.overthewire.org`
password: `cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

we are finding a line that only occues once so we use `sort data.txt | uniq -c`

password : `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

## Level 9

We use ssh again to enter the machine
`ssh -p 2220 bandit9@bandit.labs.overthewire.org`
password: `UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

We use `cat data.txt | strings | grep =`
and get

```
========== the*2i"4
=:G e
========== password
<I=zsGi
Z)========== is
A=|t&E
Zdb=
c^ LAh=3G
*SF=s
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
S=A.H&^
```

hence the password is `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`

## Level 10

we use ` cat data.txt | base64 -d`
to get

```
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

```
