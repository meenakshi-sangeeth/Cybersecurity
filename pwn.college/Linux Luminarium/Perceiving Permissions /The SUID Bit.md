### Challenge

To collect the flag by passing the SUID bit to the `/challenge/getroot` program

### Thought Process

I knew that I can set a file's SUID bit by using `chmod u+s [program]`

### Solution

I used the following commands
```bash
chmod u+s /challenge/getroot
/challenge/getroot
```
Upon execution, I got an output saying `SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...`. After that I read the flag using following command
```bash
cat /flag
```
Upon execution, I got the flag
