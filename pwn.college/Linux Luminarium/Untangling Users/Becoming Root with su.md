### Challenge

To collect the flag by gaining the root access after providing the password "hack-the-planet" 

### Thought Process

I knew that `su` (the switch user command) can be used to elevate to the root access

### Solution

I used the following command
```bash
$ su
```
Upon execution, I got the following ouput
```bash
Password: 
```
I entered the password mentioned in the challenge and then I used `cat /flag` which gave me the flag
