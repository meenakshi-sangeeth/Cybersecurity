### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "hack", output "the planet"
- If the argument is "pwn", output "college"
- If the argument is "learn", output "linux"
- For any other input, output "unknown"

### Thought Process

In bash, multiple conditions can be checked using `elif`

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "hack" ]\nthen\n    echo "the planet"\nelif [ "$1" == "pwn" ]\nthen\n    echo "college"\nelif [ "$1" == "learn" ]\nthen\n    echo "linux"\nelse\n    echo "unknown"\nfi' > /home/hacker/solve.sh
~$ /challenge/run
```
