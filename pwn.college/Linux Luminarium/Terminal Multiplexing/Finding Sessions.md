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
