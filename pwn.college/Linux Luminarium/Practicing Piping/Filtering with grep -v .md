### Challenge

To collect the flag from `/challenge/run` which will output over 1000 decoy flags (containing the word "DECOY" somewhere in the flag) mixed in with the real flag

### Thought Process

I have to filter out all the lines containing "DECOY" to get the real flag. For that, the `grep -v` command can be used which shows lines that do not match a pattern (invert match)

### Solution

```bash
/challenge/run | grep -v 'DECOY'
```

