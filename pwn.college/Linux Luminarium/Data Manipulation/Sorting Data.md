### Challenge

To collect the flag from `/challenge/flags.txt` containing 100 fake flags, with the real flag mixed among them which will be at the end when sorted alphabetically

### Thought Process

To get the flag, first I'll have to sort the flags in reverse order and output the first flag which will be the real one. To sort the flag, `sort` command can be used which by default will sort them in alphabetic order. So, `-r` should be used as an argument to sort the lines in reverse order

### Solution

```bash
sort -r /challenge/flags.txt | head -n 1
```

