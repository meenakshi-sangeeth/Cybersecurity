### Challenge

To collect the flag by looking up the help of `challenge`, which is a shell builtin, to figure out the secret value that should be passed

### Thought Process

I knew that some commands, rather than being programs with man pages and help options, are built into the shell itself called as bultins. Since it was mentioned that `challenge` is a builtin, I recalled that I can get a list of shell builtins as well as help on a specific one by passing it to the `help` which was required for this challenge

### Solution

I used the following command
```bash
help challenge
```
Upon execution, I got the following output
```bash
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "AaeG6NiH".
```
I figured I must pass "AaeG6NiH" to the argument `--secret`. Thus I used the following command
```bash
challenge --secret AaeG6NiH
```
Upon execution, I got the flag
