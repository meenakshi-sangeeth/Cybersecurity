### Challenge

To collect the flag by running `/challenge/run` after creating a `/tmp/pwn` directory and making a `college` file within it

### Thought Process

I knew that directories can be created using the `mkdir` command and files using `touch` command

### Solution

I used the following commands
```bash
mkdir /tmp/pwn
touch /tmp/pwn/college
/challenge/run
```
Upon exection, I got the flag

