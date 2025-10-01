
### Challenge

To collect the flag, 
- Launch screen
- Detach from it
- Run /challenge/run 
- Reattach

### Thought Process

Detaching can be done by entering `Ctrl-A`, followed by `d` (for detach), which leaves your session running in the background while you return to your normal terminal. To reattach, `-r` argument should be used with `screen`

### Solution

```bash
~$ screen
```
After the screen was launched, I typed in `Ctrl-A d` which showed the message `[detached from 237.pts-0.terminal-multiplexing~detaching-and-attaching]`.
Now that I'm back to the normal terminal, I executed the following which gave me the flag

```bash
~$ /challenge/run
~$ screen -r
```
