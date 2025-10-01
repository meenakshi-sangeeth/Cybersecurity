### Challenge

To collect the flag by making the `/flag` file readable

### Thought Process

I knew that `chmod` allows you to tweak permissions with the mode format of `WHO+/-WHAT`, where `WHO` is user/group/other and `WHAT` is read/write/execute

### Solution

I used the following commands 
```bash
chmod o+r /flag
cat /flag
```
Upon execution, I got the flag
