### Challenge

To collect the flag by running the shell script `/challenge/run` which has a password hardcoded into the script

### Thought Process

To get the flag, I need to read the shell script to find the hardcoded password

### Solution

```bash
~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
~$ /challenge/run
hack the PLANET
```


