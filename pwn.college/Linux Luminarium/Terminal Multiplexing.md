# Terminal Multiplexing

## 1. Launching Screen 

### Challenge

To collect the flag by launching screen

### Thought Process

To get the flag, all I've to do is type in `screen`, which is a program that creates virtual terminals inside your terminal

### Solution

```bash
screen
```

I returned to the normal terminal by pressing `Enter`, which gave me the flag 

## 2. Detaching and Attaching

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

## 3. Finding Sessions

### Challenge

To collect the flag from one of the three screen sessions

### Thought Process

When there are multiple sessions running, you can list them using `screen -ls`. The identifiers of the sessions are the PID of each respective screen process, a dot, and the name of the screen session. To attach to a specific one, you use its name or its PID by giving it as an argument to `screen -r`

### Solution

```bash
~$ screen -ls
There are screens on:
        163.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        153.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        237.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_5d4bdb750ee6465b    (Detached)
        147.session_5c286ee38161098a    (Detached)
        150.session_9dc9c83cc2a62f6c    (Detached)
6 Sockets in /home/hacker/.screen.
~$ screen -r 144
```

## 4. Switching Windows

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

## 5. Detaching and Attaching (tmux)

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

## 6. Switching Windows (tmux)

### Challenge

To collect the flag from a screen session with window 0 and window 1 which has the flag

### Thought Process

In order to switch between windows, the key combination `Ctrl-B` followed by the window number can be used

### Solution

```bash
~$ tmux a
```
Upon execution, I got window 1

```bash
cat <<MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
MSG
```
I used `Ctrl-B 0` to switch to window 0, which gave me the flag

