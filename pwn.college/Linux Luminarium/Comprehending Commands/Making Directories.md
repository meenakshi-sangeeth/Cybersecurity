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

## 11. Finding Files

### Challenge

To collect the flag which is hidden in a random directory on the filesystem

### Thought Process

I knew that the whole filesystem can be searched using `find / -name` command

### Solution

I used the following commands
```bash
find / -name flag
```
Upon exection, I got a list of files among which plenty of them were not accessible to normal user and it was mentioned that flag won't be hidden in such files. Thus I figured I'll have to read the contents of the accessible files using `cat` command. After a series of trial and error, I got the flag
