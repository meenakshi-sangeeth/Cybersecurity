### Challenge

To collect the flag by creating a shell script called `x.sh`, and running it with `bash`

### Thought Process

I knew that a shell script created and executed after naming it with a `sh` suffix and then passing it as an argument to `bash`

### Solution

I used the following command
```bash
~$ echo '/challenge/pwn' > x.sh
~$ echo '/challenge/college' >> x.sh
~$ bash x.sh
```
Upon execution, I recieved the flag
