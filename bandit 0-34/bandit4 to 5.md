# Bandit Level 4 to 5

## Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## Solution
Log in to bandit4 using `ssh bandit4@bandit.labs.overthewire.org -p 2220` and the password you found in the last challenge.  
This challenge requires us to find a file with the human-readable attribute.  
In Linux, human-readable text is represented with  `ASCII text`. This is the attribute we need to look for while hunting for that specific file.  
`ls` as usual and `cd` into the directory.
```
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
```
When we `ls` again we see a list of different files. Among these files we need to find the human-readable one.
```
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```
The `file` command is a Linux command used to determine the identity of a file by analyzing its contents. It does not rely on extensions as they can also be misleading.  
We combine this with the explicit path of the current directory, and as we want to see the file types of all the files in the directory, we add `*` after the `./`.  
This `*` is a wildcard character used to match multiple filenames or directories based on a pattern.  
So now our command looks like this `file ./*`. We can run it as it is, but a better approach would be piping the output of the first command `|` to only show us one specified file.
`grep` is a command used for searching data through lines to match defined expressions. We combine this along with `grep "ASCII text"` and run our command.
```
bandit4@bandit:~/inhere$ file ./* | grep "ASCII text"
./-file07: ASCII text
```
We found the only human-readable file, now just `cat` it.
```
bandit4@bandit:~/inhere$ cat ./-file07
XXXBANDIT5PASSWORDXXX
