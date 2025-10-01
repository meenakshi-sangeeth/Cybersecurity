### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes two arguments
- Outputs them in REVERSE order (second argument first, then the first argument)

### Thought Process

The first and second argument can be accessed by the script using special variables `$1` and `$2` respectively

### Solution

```bash
~$ echo '#!/bin/bash' > /home/hacker/solve.sh
~$ echo 'echo "$2 $1"' >> /home/hacker/solve.sh
~$ /challenge/run
```
