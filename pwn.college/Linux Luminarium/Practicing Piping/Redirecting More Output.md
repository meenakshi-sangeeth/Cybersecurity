### Challenge

To collect the flag after redirecting the output of `/challenge/run` to the file `myflag`

### Thought Process

I knew that `>` can be used to redirect the output of any command. Thus if I use `>` between `/challenge/run` and `myflag`, I'll be able to redirect the output as the challenge requires

### Solution

I used the following commands
```bash
/challenge/run > myflag
cat myflag
```
Upon execution, I got the flag
