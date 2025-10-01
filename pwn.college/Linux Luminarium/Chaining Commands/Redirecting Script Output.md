### Challenge

To collect the flag by piping the output of the script into a single invocation of the `/challenge/solve` command

### Thought Process

I recalled that `|` operator redirects standard output of one command to another. Thus I will have to use `|` operator to pipe the output of the script to `/challenge/solve`

### Solution

I used the following command
```bash
bash x.sh | /challenge/solve
```
Upon execution, I got the flag
