### Challenge

To collect the flag by piping `/challenge/pwn` into `/challenge/college` after intercepting the data to see what pwn needs from you

### Thought Process

I knew that `tee` command duplicates data flowing through your pipes to any number of files provided on the command line. Thus for intercepting the data I'll have to use `tee`

### Solution

I used the following command
```bash
/challenge/pwn | tee code | /challenge/college
cat code
```
Upon execution, I got the following output
```bash
Usage: /challenge/pwn-secret [SECRET_ARG]
SECRET_ARG should be "kNkC3zyg"
```
Thus I used the following command
```bash
/challenge/pwn--secret kNkC3zyg | /challenge/college
```
Upon execution, I got the flag
