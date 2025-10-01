### Challenge

To collect the flag by redirecting the output of `/challenge/run`, to `myflag` and the errors  to `instructions`

### Thought Process

I knew that if there's a command that might produce data via standard error, I  can redirect standard error (FD 2) to the a file using `2>` between the command and the file

### Solution

I used the following commands
```bash
/challenge/run > myflag 2> instructions
cat myflag
```
Upon execution, I got the flag
