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
