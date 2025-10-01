### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output nothing

### Thought Process

In bash, `if` statement can be used to make decisions. Thus I can check if the argument is "pwn" or not using `if` statement

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n  echo "college"\nfi' > /home/hacker/solve.sh 
~$ /challenge/run
```
