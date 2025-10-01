### Challenge

To collect the flag by locating `win` command in `$PATH` and reading the `flag` file in that directory

### Thought Process

I can use `which` to find where the `win` command is located and then `cat` the `flag` file from that same directory
 
### Solution

```bash
~$ which win
/challenge/paths/16937/win
~$ cat /challenge/paths/16937/flag
```

