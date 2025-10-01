### Challenge

To collect the flag by changing the group ownership of the flag file, and reading it by invoking `chgrp` as the hacker user

### Thought Process

I knew that group ownership can be changed with the `chgrp` (change group) command

### Solution

I used the following commands
```bash
chgrp hacker /flag
cat /flag
```
Upon execution, I got the flag
