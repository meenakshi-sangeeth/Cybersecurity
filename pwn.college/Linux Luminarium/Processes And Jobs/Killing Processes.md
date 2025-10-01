### Challenge

To collect the flag by finding the `dont_run` process and kill it since `/challenge/run` will refuse to run while `/challenge/dont_run` is running

### Thought Process

I knew that `kill` can be used to terminate a process by passing the process identifier (the PID from ps) as an argument

### Solution

I executed the following command
```bash
ps aux | grep /challenge/dont_run
```
I got the following output
```bash
hacker        73  0.0  0.0   4976  3200 ?        Ss   18:27   0:00 /challenge/dont_run
hacker      1353  0.0  0.0   4140  1920 pts/0    S+   18:32   0:00 grep --color=auto /challenge/dont_run
```
Now that I know PID, I used the following commands
```bash
kill 73
/challenge/run
```
Upon execution, I got the flag
