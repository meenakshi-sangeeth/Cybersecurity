# Processes And Jobs

## 1. Listing Processes

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

## 2. Killing Processes

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

## 3. Interrupting Processes

### Challenge

To collect the flag by interrupting `/challenge/run`

### Thought Process

I knew that a process can be interrupted by holding down the Ctrl key and pressing C

### Solution

I executed the following command
```bash
/challenge/run
```
I got the following output
```bash
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
```
Thus I entered Ctrl-C which gave me the flag

## 4. Suspending Processes

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

## 5. Resuming Processes

### Challenge

To collect the flag by suspending `/challenge/run` and then resuming it

### Thought Process

I knew that a process can be suspended by holding down the Ctrl key and pressing Z

### Solution

I executed the following command
```bash
/challenge/run
```
I got the following output
```bash
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
```
Thus I entered Ctrl-Z after which I executed `fg` which gave me the flag

## 4. Suspending Processes

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

## 6. Backgrounding Processes

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

## 7. Foregrounding Processes

### Challenge

To collect the flag by involving the usage of `fg`

### Thought Process

I knew that `fg` is used to foreground a process

### Solution

I executed the following command
```bash
/challenge/run
```
I got the following output
```bash
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
```
Thus I entered Ctrl-Z after which I used `bg` which gave me the following output
```bash
Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.
```
As per the instruction I used the following commands
```bash
fg
/challenge/run
```
Upon execution, I got the flag

## 8. Starting Backgrounded Processes

### Challenge

To collect the flag by launching `/challenge/run` backgrounded

### Thought Process

I knew that a process can be backgrounded without suspending it by appending `&` to the command

### Solution

I executed the following command
```bash
/challenge/run &
```
Upon execution, I got the flag

## 9. Process Exit Codes

### Challenge

To collect the flag by retrieving the exit code returned by `/challenge/get-code` and then running `/challenge/submit-code` with that error code as an argument

### Thought Process

I knew that the exit code of the most recently-terminated command can be accessed using the special `?` variable. I had to make sure that I prepend the variable with `$` to read its value

### Solution

I used the following command
```bash
 /challenge/get-code
```
Upon execution, I got an output saying `Exiting with an error code!` after which I used `echo $?` which gave `38` as the output. 
Thus, I used the following command
```bash
/challenge/submit-code 38
```
Upon execution, I got the flag

