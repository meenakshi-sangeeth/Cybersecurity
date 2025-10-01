### Challenge

To collect the flag by redirecting the PWN file to `/challenge/run` and have the PWN file contain the value COLLEGE

### Thought Process

I knew that I can redirect input to programs using `<` and I recalled that for output redirection I'll have to use `>`. Thus for the PWN file to contain COLLEGE I'll have to use `>` and to redirect PWN file to `/challenge/run`, I'll have to use `<`

### Solution

I used the following commands
```bash
echo COLLEGE > PWN
/challenge/run < PWN
```
Upon execution, I got the flag
