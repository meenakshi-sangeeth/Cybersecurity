### Challenge

To collect the flag by grepping for it after running `/challenge/run` using pipe operator

### Thought Process

I knew that standard output from the command to the left of the pipe operator will be connected to (piped into) the standard input of the command to the right of the pipe. Thus if I use `|` (pipe) operator between `/challenge/run` and `grep` I'll be able to meet the requirements of the challenge

### Solution

I used the following command
```bash
/challenge/run | grep pwn.college 
```
Upon execution, I got the flag
