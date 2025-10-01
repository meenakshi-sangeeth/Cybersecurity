### Challenge

To collect the flag using process substitution and compare the outputs of `/challenge/print_decoys` which will print a bunch of decoy flags and `/challenge/print_decoys_and_flag` which will print those same decoys plus the real flag

### Thought Process

Since the second command contains all the decoys plus one additional line (the real flag), I'll have to use `diff` to reveal the flag

### Solution

```bash
diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
```
