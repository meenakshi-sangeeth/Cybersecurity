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
