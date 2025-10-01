### Challenge

To collect the flag, run `/challenge/run`, extract the second column and join them into a single line

### Thought Process

To extract the second column, `cut` command can be used with `-d` argument which specifies the column delimiter and `-f` argument which specifies the field number

### Solution

```bash
/challenge/run | cut -d " " -f 2 | tr -d "\n"
```
