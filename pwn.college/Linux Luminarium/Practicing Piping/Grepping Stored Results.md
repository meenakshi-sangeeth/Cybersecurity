### Challenge

To collect the flag by following the given instructions:
1. Redirect the output of `/challenge/run` to `/tmp/data.txt`
2. This will result in a hundred thousand lines of text, with one of them being the flag, in `/tmp/data.txt`
3. Grep that for the flag!

### Thought Process

I knew that redirecting of the output can be done using `>` and searching through the resulting file using `grep`

### Solution

I used the following command
```bash
/challenge/run > /tmp/data.txt
```
As mentioned in the challenge, the execution of the above command lead to an output of hundred thousand lines of text, through which I searched for the flag using the following command
```bash
grep "pwn.college" /tmp/data.txt
```
Upon execution, I got the flag
