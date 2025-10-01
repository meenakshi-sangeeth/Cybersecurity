### Challenge

To collect the flag by running `challenge/run` after creating an executable script at `/home/hacker/solve.sh` that has a proper shebang and outputs "hack the planet"

### Thought Process

A shebang is the `#!/bin/bash` line at the beginning of the script that tells the system which interpreter to use

### Solution

```bash
~$ echo '#!/bin/bash' > /home/hacker/solve.sh
~$ echo 'echo "hack the planet"' >> /home/hacker/solve.sh
~$ /challenge/run
```
