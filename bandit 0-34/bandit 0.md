# Bandit Level 0

## Level Goal
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

## Solution
This level requires basic usage of the `ssh` command. As the port number is already specified, we can login to `bandit0` with the following command:

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
When prompted for a password enter `bandit0`

Here:
- `bandit0` is the username
- `bandit.labs.overthewire.org` is the hostname
- `-p 2220` is specifying the port number

