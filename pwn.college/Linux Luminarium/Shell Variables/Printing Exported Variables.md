### Challenge

To collect the flag by finding the FLAG variable using the `env` command

### Thought Process

I knew that `env` will print out every exported variable set in your shell and thus if I search through the output after executing `env` command I'll be able to find the FLAG variable

### Solution

I used the following command
```bash
env
```
Upon execution, I got a list of exported variables from which I got the flag
