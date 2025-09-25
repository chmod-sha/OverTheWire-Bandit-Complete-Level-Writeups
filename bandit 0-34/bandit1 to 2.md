# Bandit Level 1 to 2

## Level Goal
The password for the next level is stored in a file called - located in the home directory.

## Solution
Log in to bandit1 using `ssh bandit1@bandit.labs.overthewire.org -p 2220` and the password you found in the last challenge.  
As we did previously, first check if the given file name is actually present in our current directory with the `ls` command.  
```
bandit1@bandit:~$ ls
-
```
Now, to read the contents of this file simply using the `cat` command on it will not work, as `-` is often treated as a special placeholder for many Linux commands. When run with `cat`, the terminal interprets it as a placeholder for `stdin`. Hence, after pressing enter, it hangs waiting for you to type something.  
`.` in Linux represents the current working directory. When we type `./-` we're telling the terminal to read the contents of this file by using an explicit path.
```
bandit1@bandit:~$ cat ./-
XXXBANDIT2PASSWORDXXX
```
