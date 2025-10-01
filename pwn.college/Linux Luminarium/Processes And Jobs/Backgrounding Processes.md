### Challenge

To collect the flag by launching `/challenge/run` , then suspending it, then backgrounding it with `bg` and launching another copy while the first is running in the background

### Thought Process

I knew that a process can be resumed in the background with the `bg` which will allow the process to keep running, while giving you your shell back to invoke more commands in the meantime command

### Solution

I executed the following command
```bash
/challenge/run
```
I got the following output
```bash
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         274 S+   bash /challenge/run
root         276 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
```
Thus I entered Ctrl-Z after which I used the following commands
```bash
bg
/challenge/run
```
Upon execution, I got the flag
