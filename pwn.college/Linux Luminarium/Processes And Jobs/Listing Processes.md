### Challenge

To collect the flag by finding `/challenge` in the running process list, figuring out the filename, and relaunching it directly

### Thought Process

I knew that `ps aux` can be used to output the running process list and I figured if I `grep` for `/challenge` I'll be able to find the filename

### Solution

I executed the following command
```bash
ps aux | grep /challenge/
```
I got the following output
```bash
root          68  0.0  0.0   4132  2560 ?        S    18:17   0:00 /challenge/11390-run-12446
hacker       724  0.0  0.0   4140  2560 pts/1    S+   18:20   0:00 grep --color=auto /challenge/
```
Now that I know the filename, I used the following command
```bash
/challenge/11390-run-12446
```
Upon execution, I got the flag
