### Challenge

To collect the flag by reading the file `/challenge/data.txt` using `grep` command

### Thought Process

I knew that grep will search the file for lines of text containing the argument and print them to the console. It was given as a hint that flag always starts with the text pwn.college. Thus I figured that I'll have to pass pwn.college as the argument

### Solution

I used the following command
```bash
grep pwn.college /challenge/data.txt
```
Upon execution, I got the flag
