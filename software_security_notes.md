# Linux Lecture

- dev/null is a blackhole for file
- <ctrl-r> is used to reverse search stuff.

## xargs 
Allows you to open a program in an automated way 

## Strace 
- Shows whats happening internally
- `strace` outputs to stderr
- sometimes better than `gdb`

## tar
Use it to pack and unpack. 

# File Permissions in Linux 
- to see all users go to `etc/passwd`
- every user has a user Id and a name
- Enables protection from other users
- enables protextion of system code from users 
- Root user has `id = 0`
- linux is multiuser and multiprocess
- every process has an owner. When a process wants to do something the kernel checks the owner can do it and then allows or disallows the process. 
- android has one user per app. 
- `/etc/groups/` shows all the groups 
- correct way to do docker/wireshark create a group that is allowed to do those specific functions 
- `sudo` allows you to run stuff as root (`sudo -i` or `sudo bash` can be used to get a full sudo shell.)


