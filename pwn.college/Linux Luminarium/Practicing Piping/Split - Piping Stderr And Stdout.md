### Challenge

To collect the flag by combining the usage of `>()`, `2>`, and `|` with the following:
- `/challenge/hack`: this produces data on stdout and stderr
- `/challenge/the`: you must redirect hack's stderr to this program
- `/challenge/planet`: you must redirect hack's stdout to this program

### Thought Process

In order to redirect stderr of `/challenge/hack` to I'll have to use `2>` as well as process substitution `>()` to feed the `stderr` output into `/challenge/the`. After that `|` operator should be used to pipe stdout of `/challenge/hack` into `/challenge/planet`

### Solution

I used the following command
```bash
/challenge/hack 2> >( /challenge/the ) | /challenge/planet
```
Upon execution, I got the flag
