### Challenge

To collect the flag by setting the variable PWN to COLLEGE YEAH

### Thought Process

I knew that when the shell sees a space, it ends the variable assignment and interprets the next word as a command. Thus if I have to assign a value with space in between, I'll have to enclose the value in double quotes (")

### Solution

I used the following command
```bash
PWN="COLLEGE YEAH"
```
Upon execution, I got the flag
