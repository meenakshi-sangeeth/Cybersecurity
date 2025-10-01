### Challenge

To collect the flag, run `/challenge/run`, but it prints the flag with swapped letter cases

### Thought Process

`tr` is a command which translates the character provided in its first argument to the character provided in its second argument. It can also handle multiple characters, with the characters in different positions of the first argument replaced with associated characters in the second argument.

### Solution

```bash
/challenge/run | tr 'A-Za-z' 'a-zA-Z'
```
