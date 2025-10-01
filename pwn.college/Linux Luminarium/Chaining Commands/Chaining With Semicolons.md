### Challenge

To collect the flag by running `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon

### Thought Process

I knew that `;` is used to chain commands. Basically, when you hit Enter, your shell executes your typed command and, after that command terminates, give you the prompt to input another command. The semicolon is analogous, just without the prompt and with you entering both commands before anything is executed

### Solution

I used the following command
```bash
/challenge/pwn; /challenge/college
```
Upon execution, I got the the flag
