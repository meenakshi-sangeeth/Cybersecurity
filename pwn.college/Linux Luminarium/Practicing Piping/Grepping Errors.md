### Challenge

To collect the flag by grepping through the errors after running `/challenge/run` using pipe operator

### Thought Process

I recalled that if I have to grep through errors, first, I'll have to redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)

### Solution

I used the following command
```bash
/challenge/run 2>&1 | grep "pwn.college"
```
Upon execution, I got the flag
