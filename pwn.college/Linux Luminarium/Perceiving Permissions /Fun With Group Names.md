### Challenge

To collect the flag by figuring out the name of the group that your user is in, and then invoking `chgrp`

### Thought Process

I knew that to figure out the name of the group that the user is in, I'll have to use `id` command

### Solution

I used `id` which gave me the following output
```bash
uid=1000(hacker) gid=1000(grp28569) groups=1000(grp28569)
```
Thus I figured that the names of the group is `grp28569` and I used the following commands
```bash
chgrp grp28569 /flag
cat /flag
```
Upon execution, I got the flag
