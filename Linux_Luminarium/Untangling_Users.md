# Untangling Users

## 1. Becoming root with su

### Challenge

To collect the flag by gaining the root access after providing the password "hack-the-planet" 

### Thought Process

I knew that `su` (the switch user command) can be used to elevate to the root access

### Solution

I used the following command
```bash
$ su
```
Upon execution, I got the following ouput
```bash
Password: 
```
I entered the password mentioned in the challenge and then I used `cat /flag` which gave me the flag

## 2.Other user with su 

### Challenge

To collect the flag by switching to the zardus user with the password "dont-hack-me" and then running `/challenge/run`

### Thought Process

While executing `su` I knew that I can also give a username as an argument to switch to that user instead of root

### Solution

I used the following command
```bash
su zardus
```
Upon execution, it prompted me to enter the password and I entered the password mentioned in the challenge. After that I executed `/challenge/run` which gave me the flag

## 3. Cracking Passwords

### Challenge

To collect the flag by cracking a leak of `/etc/shadow` (in /challenge/shadow-leak) and then `su` to zardus and run `/challenge/run`

### Thought Process

I knew that if I get access to a leaked /etc/shadow, I can start cracking passwords using ` john --show shadow-leak`. This will give me an output separated by :s, where the first field of each line is the username and the second is the password

### Solution

I used the following commands
```bash
cd /challenge
/challenge$ john --show shadow-leak
```
Upon execution, I got the following output
```bash
hacker:NO PASSWORD:20000:0:99999:7:::
zardus:aardvark:20015:0:99999:7:::

2 password hashes cracked, 0 left
```
Now that I knew the password, I executed `su zardus` which prompted to give the password. I entered `aardvark` as the password and executed `/challenge/run` which gave me the flag

## 4. Using sudo

### Challenge

To collect the flag by reading the `flag` file with the usage of `sudo`

### Thought Process

I knew that sudo (superuser do) defaults to running a command as root without authenticating via password

### Solution

I used the following commands one by one
```bash
sudo cat /flag
```
Upon execution, I got the flag
