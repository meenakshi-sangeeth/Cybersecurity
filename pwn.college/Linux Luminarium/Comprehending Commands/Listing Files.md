### Challenge

To collect the flag by listing the files in /challenge

### Thought Process

I knew that `ls` command will list all the files in the directory provided to it as argument. 

### Solution

I used the following command
```bash
ls /challenge
```
Upon execution, I got the following ouptut
```bash
hacker@commands-listing-files:~$ ls /challenge
15153-renamed-run-4699 DESCRIPTION.md
```
I figured that the flag will be in `15153-renamed-run-4699` since it was mentioned that `/challenge/run` is renamed with some random name. Thus I used the following command
```bash
/challenge/15153-renamed-run-4699 
```
Upon execution, I got the flag
