### Challenge

To collect the flag by reading the flag file by its absolute path without using the `cd` command

### Thought Process

In the terminal it was shown that the location of the flag file is `/usr/include/bsd/flag`. I knew that if I give the given file path as the argument to `cat` command, the contents of the file will be read without using `cd` command 

### Solution

I used the following command
```bash
cat /usr/include/bsd/flag
```
Upon execution, I got the flag
