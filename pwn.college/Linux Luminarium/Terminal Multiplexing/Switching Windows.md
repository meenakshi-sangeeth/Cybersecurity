### Challenge

To collect the flag from a screen session with window 0 and window 1 which has the flag

### Thought Process

In order to switch between windows, the key combination `Ctrl-A` followed by the window number can be used

### Solution

```bash
~$ screen -r
```
Upon execution, I got window 1

```bash
cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
```

I used `Ctrl-A 0` to switch to window 0, which gave me the flag
