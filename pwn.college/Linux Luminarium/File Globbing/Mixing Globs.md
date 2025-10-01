### Challenge

To collect the flag by changing the directory to `/challenge/files` and write a single, short (6 characters or less) glob that will match the files "challenging", "educational", and "pwning"

### Thought Process

Since there's no common pattern of characters in the files mentioned, I figured I'll have to use a comination of `[ ]` and `*` globs and pass "cep" to `[ ]` which will meet the requirements of the challenge

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run [cep]*
```
Upon execution, I got the flag
