### Challenge

To collect the flag, 
- Launch tmux
- Detach from it
- Run /challenge/run 
- Reattach

### Thought Process

`tmux` (terminal multiplexer) does all the same things as `screen` but with some different key bindings. Instead of Ctrl-A, tmux uses Ctrl-B as its command prefix and for reattaching, `tmux attach` or `tmux a` is used

### Solution

```bash
~$ tmux
```
After the session was launched, I typed in `Ctrl-B d` to detach from it.
Now that I'm back to the normal terminal, I executed the following which gave me the flag

```bash
~$ /challenge/run
~$ tmux a
```
