### Challenge

To collect the flag by running `/challenge/run` with an append-mode redirect of the output to the file /home/hacker/the-flag

### Thought Process

I knew that `>>` should be used if I want the output of a bunch of commands to keep appending to the same file since `>` will create a new output file every time, deleting the old contents

### Solution

I used the following commands
```bash
 /challenge/run >> /home/hacker/the-flag
cat /home/hacker/the-flag
```
Upon execution, I got the flag
