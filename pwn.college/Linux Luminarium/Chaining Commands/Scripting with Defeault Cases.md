### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output "nope"

### Thought Process

In bash, `if` statement can be used to make decisions. Thus I can check if the argument is "pwn" or not using `if` statement and output "college" if it matches using `then`. Otherwise "nope" can be outputted using `else`

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n    echo "college"\nelse\n    echo "nope"\nfi' > /home/hacker/solve.sh
~$ /challenge/run
```
