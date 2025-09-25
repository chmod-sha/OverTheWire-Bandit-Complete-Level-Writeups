# Bandit Level 0 to 1

## Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
## Solution
This level requires us to read contents from a file called `readme` present in our current directory (home directory) as user bandit0. First, we need to check if this file is actually present.
`ls` is a command we use for listing files in our current directory. After running this command we can see there is indeed a file named `readme` present.
```
bandit0@bandit:~$ ls
readme
```
For viewing the contents of a file, we use a command called `cat`, which is short for concatenate.
```
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is:   XXXBANDIT1PASSWORDXXX
```
