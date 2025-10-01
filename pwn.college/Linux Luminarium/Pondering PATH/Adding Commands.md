### Challenge

To collect the flag by making a shell script called `win`, add its location to the `PATH` and enable `/challenge/run`

### Thought Process

For this challenge, first I need to create a `win` script and then add it to `PATH` but instead of overwriting it I'll append to the existing `PATH` to avoid issues with `cat` not being found

### Solution

```bash
~$ echo '#!/bin/bash' > /tmp/win
~$ echo 'cat /flag' >> /tmp/win
~$ chmod +x /tmp/win
~$ export PATH=/tmp:$PATH
~$ /challenge/run
```
