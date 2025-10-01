### Challenge

To collect the flag by cracking a leak of `/etc/shadow` (in /challenge/shadow-leak) and then `su` to zardus and run `/challenge/run`

### Thought Process

I knew that if I get access to a leaked /etc/shadow, I can start cracking passwords using ` john --show shadow-leak`. This will give me an output separated by :s, where the first field of each line is the username and the second is the password

### Solution

I used the following commands
```bash
cd /challenge
/challenge$ john --show shadow-leak
```
Upon execution, I got the following output
```bash
hacker:NO PASSWORD:20000:0:99999:7:::
zardus:aardvark:20015:0:99999:7:::

2 password hashes cracked, 0 left
```
Now that I knew the password, I executed `su zardus` which prompted to give the password. I entered `aardvark` as the password and executed `/challenge/run` which gave me the flag
