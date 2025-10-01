### Challenge

To collect the flag by reading `/challenge/read_me` into the PWN environment variable with a single command as `/challenge/read_me` will keep changing

### Thought Process

I recalled that I can read user input into a variable using `read` and I can  redirect files into command input using `<`. Thus if I use both of these together in a single command I'll be able to complete the challenge

### Solution

I used the following command
```bash
read PWN < /challenge/read_me
```
After execution, I got the flag

