### Challenge

To collect the flag, pipe the first 7 lines of `/challenge/pwn` into `/challenge/college`

### Thought Process

To get the first 7 lines, `/challenge/pwn` can be piped with `head`. It's a command used to display the first few lines of its input

### Solution

```bash
/challenge/pwn | head -n 7 | /challenge/college
```
