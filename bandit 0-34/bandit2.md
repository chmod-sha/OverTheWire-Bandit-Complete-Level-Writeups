# Bandit Level 2

## Level Goal
The password for the next level is stored in a file called - located in the home directory.

## Solution
Login to bandit1 using `ssh bandit1@bandit.labs.overthewire.org -p 2220` and the password you found in the last challenge.
As we did previously, first check if a file named is actually present in our current directory with the `ls` command.  
```
bandit1@bandit:~$ ls
-
```
Now, to read the contents of this file simply using the `cat` command on it will not work, as `-` is a special placeholder for many linux commands and the linux terminal interprets it as stdin when ran with `cat`. Hence, after pressing enter it hangs waiting for you to type something.  
`.` in linux represents the current working directory. When we type `./-` it is us telling the terminal to read this file with an explicit path.
```
bandit1@bandit:~$ cat ./-
XXXBANDIT2PASSWORDXXX
```
