### Challenge

To collect the flag, run `/challenge/run`, but it has some decoy characters like ^ and %

### Thought Process

To get the correct flag, I'll have to delete the decoy characters. For that, `tr` can be used with `-d` and an argument of what characters to delete

### Solution

```bash
/challenge/run | tr -d ^%
```
