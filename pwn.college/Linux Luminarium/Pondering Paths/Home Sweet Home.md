### Challenge

To collect the flag by executing `/challenge/run` command by specifying a file path as an argument with the following constraints:
1. Your argument must be an absolute path.
2. The path must be inside your home directory.
3. Before expansion, your argument must be three characters or less

### Thought Process

I knew that `~` is shorthand for `/home/hacker`, which is my home directory in Dojo. Since the path had to be within my home directory and the argument could be only three characters or less, I figured that using `~` would meet the given constraints. Thus I would have to prepend `~/` to the file name which should be a single character to meet the constraints.

### Solution

I used the following command
```bash
/challenge/run ~/f
```
Upon execution, I got the flag
