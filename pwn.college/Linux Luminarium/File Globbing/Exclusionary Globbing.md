### Challenge

To collect the flag by running `/challenge/run` with all files that don't start with "p", "w", or "n" after changing your directory to `/challenge`

### Thought Process

I recalled that if the first character in the brackets is a `!` or (in newer versions of bash) a `^`, the glob inverts, and that bracket instance matches characters that aren't listed. Thus I figured I'll have to use `!` or `^` to match with the files that don't start with "p", "w", or "n"

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run [!pwn]*
```
Upon execution, I got the flag
