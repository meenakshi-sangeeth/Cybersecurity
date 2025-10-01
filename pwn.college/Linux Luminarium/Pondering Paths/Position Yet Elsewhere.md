### Challenge

To collect the flag by executing the `/challenge/run` program from a specific path 

### Thought Process

To complete the challenge, I needed to move to the correct directory using `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command:
`/challenge/run`
This gave me the following output
```bash
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
```
Thus I found out the correct directory which is /etc

### Solution

I navigated to the right directory using the command
```bash
cd /etc
```
After that I executed the command `/challenge/run` which gave me the flag
