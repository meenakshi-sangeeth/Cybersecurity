### Challenge

To collect the flag by running `/challenge/hack` and duplicating its output as input to both the `/challenge/the` and the `/challenge/planet` commands

### Thought Process

In order to duplicate the output of `/challenge/hack` into both `/challenge/the` and the `/challenge/planet` , I knew I would have to make use of process substitution with the command `tee`

### Solution

I used the following command
```bash
/challenge/hack | tee >( /challenge/the ) >( /challenge/planet )
```
Upon execution, I got the flag
