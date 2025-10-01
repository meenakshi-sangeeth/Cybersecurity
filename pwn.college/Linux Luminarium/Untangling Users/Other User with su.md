### Challenge

To collect the flag by switching to the zardus user with the password "dont-hack-me" and then running `/challenge/run`

### Thought Process

While executing `su` I knew that I can also give a username as an argument to switch to that user instead of root

### Solution

I used the following command
```bash
su zardus
```
Upon execution, it prompted me to enter the password and I entered the password mentioned in the challenge. After that I executed `/challenge/run` which gave me the flag
