
# Bandit Level 3

## Level Goal
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory  

## Solution
Login to bandit2 using `ssh bandit2@bandit.labs.overthewire.org -p 2220` and the password you found in the last challenge.  
As we did previously, first check if a file with this name is actually present in our current directory with the `ls` command.  
```
bandit2@bandit:~$ ls
--spaces in this filename--
```
To read the contents of this file simply using the `cat` command on it will not work, same as the previous level. 
```
bandit2@bandit:~$ cat --spaces in this filename--
cat: unrecognized option '--spaces'
Try 'cat --help' for more information.
```
Here, this error pops up because when `cat` sees `--spaces` it automatically thinks we are giving it an option, NOT a filename.  
In linux, anything starting with `-` or `--` is treated like a flag unless you specify otherwise.  
Anything in linux with spaces psent in it's names is viewed with `" "`(example `"spaces in this filename")`. Here we have `--` as well, so to view the file we will use the `""` along with defining it's explicit path as we did in the last level.  
```
bandit2@bandit:~$ cat ./"--spaces in this filename--"
XXXBANDIT3PASSWORDXXX
```
