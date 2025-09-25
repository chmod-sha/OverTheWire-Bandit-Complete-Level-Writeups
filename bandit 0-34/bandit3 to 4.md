
# Bandit Level 3 to 4

## Level Goal
The password for the next level is stored in a hidden file in the inhere directory.  

## Solution
Log in to bandit3 using `ssh bandit3@bandit.labs.overthewire.org -p 2220` and the password you found in the last challenge.  
This challenge requires us to find a hidden file in a directory named `inhere`. When we `ls` we see there is indeed a directory with this name.
```
bandit3@bandit:~$ ls
inhere
```
To switch to this directory from our current directory there is a Linux command called `cd` which quite literally stands for change directory. For this to work we specify the directory or path of our choice along with it.
```
bandit3@bandit:~$ cd inhere
```
We now check our current directory with the `pwd` command and it shows we are now in the `inhere` directory.
```
bandit3@bandit:~/inhere$ pwd
/home/bandit3/inhere
```
We now run `ls` but it does not show anything as the level goal mentions that the file is hidden.
```
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$
```
To find hidden files in Linux, there is a command called `find`. Simply type it into the terminal and it will show all the files that are hidden in our directory.
```
bandit3@bandit:~/inhere$ find
.
./...Hiding-From-You
```
Alternatively, we can also modify the `ls` command to show hidden files. The `-a` flag with the `ls` command (a command-line argument) shows the name of the various files and folders of the current directory, including all the hidden files.
```
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
```
Now just `cat` the file as we have previously done.
```
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You
XXXBANDIT4PASSWORDXXX
```

