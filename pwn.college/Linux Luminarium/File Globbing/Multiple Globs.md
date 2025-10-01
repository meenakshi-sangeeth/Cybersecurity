### Challenge

To collect the flag by running `/challenge/run` in `/challenge/files`, providing a single argument of 3 characters or less, that covers every word that contains the letter p

### Thought Process

Bash supports the expansion of multiple globs in a single word. Thus I can use `*` glob before and after the letter p thereby covering every word containing the letter p

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run *p*
```
Upon execution, I got the flag
