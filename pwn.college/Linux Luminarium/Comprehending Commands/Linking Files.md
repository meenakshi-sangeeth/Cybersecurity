### Challenge

To collect the flag which is in `/flag`, but `/challenge/catflag` will instead read out `/home/hacker/not-the-flag` thereby requiring the use of symlink

### Thought Process

I knew that symbolic links are created with the ln command with the -s argument where the original file path comes before the link path in the command

### Solution

I used the following commands
```bash
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag
```
Upon exection, I got the flag
