### Challenge

To collect the flag using tab completion from `/challenge/files`, which has a bunch of files starting with `pwncollege`

### Thought Process

When there are multiple options for tab completion, by default bash will auto-expand until the first point. When you hit tab a second time, it'll print out those options

### Solution

```bash
~$ cat /challenge/p<TAB><TAB>
pwn                    pwncollege-family      pwncollege-flyswatter
pwn-college            pwncollege-flag        pwncollege-hacking
pwn-the-planet         pwncollege-flamingo
~$ cat /challenge/pwncollege-flag
```
