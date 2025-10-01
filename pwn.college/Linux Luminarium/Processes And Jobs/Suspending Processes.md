### Challenge

To collect the flag by suspending `/challenge/run`

### Thought Process

I knew that a process can be suspended by holding down the Ctrl key and pressing Z

### Solution

I executed the following command
```bash
/challenge/run
```
I got the following output
```bash
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         319     171  0 06:46 pts/0    00:00:00 bash /challenge/run
root         321     319  0 06:46 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
```
Thus I entered Ctrl-Z after which I executed `/challenge/run` which gave me the flag
