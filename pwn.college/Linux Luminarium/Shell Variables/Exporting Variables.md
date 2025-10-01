### Challenge

To collect the flag by invoking `/challenge/run` with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported

### Thought Process

I knew that variables that you set in a shell session are local to that shell process and thus if I have to export them, I'll have to use `export` before the variable that needs to be exported

### Solution

I used the following commands one by one
```bash
PWN=COLLEGE
export PWN
COLLEGE=PWN
/challenge/run
```
Upon execution, I got the flag
