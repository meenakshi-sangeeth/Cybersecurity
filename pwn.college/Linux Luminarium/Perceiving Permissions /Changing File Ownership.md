### Challenge

To collect the flag by changing the owner of the `/flag` file to the hacker user

### Thought Process

I knew that changing of the ownership of files can be done using `chown` (change owner) command followed by the username and filename 

### Solution

I used the following commands
```bash
chown hacker /flag
cat /flag
```
Upon execution, I got the flag
