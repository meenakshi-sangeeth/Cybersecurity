### Challenge

To collect the flag by disrupting the operation of the `/challenge/run` program in such a way that the program can't find the `rm` command since it delete the flag using `rm`

### Thought Process

I knew that there is a special shell variable, called `PATH`, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. Thus if I use `PATH`, I will be able to obtain the flag

### Solution

I used the following commands
```bash
PATH=""
/challenge/run
```
Upon execution, I got the the flag
