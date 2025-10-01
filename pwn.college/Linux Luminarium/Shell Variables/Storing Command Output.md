### Challenge

To collect the flag by reading the output of the `/challenge/run` command directly into a variable called PWN

### Thought Process

I recalled that if I want to store the output of some command into a variable command substitution has to be used. It can be done by enclosing the command in the brackets of `$()`

### Solution

I used the following commands
```bash
PWN=$( /challenge/run)
echo $PWN
```
Upon execution, I got the flag
