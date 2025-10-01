### Challenge

To collect the flag by writing the word PWN to the filename COLLEGE using `>`

### Thought Process

I knew that `>` is used to redirect stdout to files. Thus if I use `>` between `echo PWN` and `COLLEGE`, I'll be able to complete the challenge

### Solution

I used the following command
```bash
echo PWN > COLLEGE
```
Upon execution, I got the flag
