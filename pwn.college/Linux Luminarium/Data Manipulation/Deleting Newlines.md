### Challenge

To collect the flag, run `/challenge/run`, but it has a bunch of newlines 

### Thought Process

To get the correct flag, I'll have to delete the newlines. For that, `tr` can be used with `-d` and `\n` which is the standin for newline as the argument 

### Solution

```bash
/challenge/run | tr -d "\n"
```
