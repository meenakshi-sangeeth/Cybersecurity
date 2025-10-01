
### Challenge

To collect the flag, kill the decoy process holding the `/tmp/flag_fifo` so `/challenge/run` can write the real flag into the FIFO, then read the FIFO to reveal the flag

### Thought Process

Firstly I'll have to check what processes are running. Then find `/challenge/decoy` in the list and kill it with its process ID. After that I'll run `/challenge/run` to get the flag


### Solution

Terminal 1
```bash
cat /tmp/flag_fifo
```
Terminal 2
```bash
ps -ef | grep /challenge/decoy
```
Now that I know the filename, I used the following command
```bash
~$ ps -ef | grep /challenge/decoy
root         139       1  0 15:48 ?        00:00:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       142     139  0 15:48 ?        00:00:00 /usr/bin/python /challenge/decoy
hacker       337     292  0 15:49 pts/1    00:00:00 grep --color=auto /challenge/decoy
~$ kill 142
~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
```
I got the flag in terminal 1
