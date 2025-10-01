### Challenge

To collect the flag by invoking `/challenge/solve`, making it executable, and running it without explicitly invoking `bash`

### Thought Process

I knew that instead of manually invoking `bash` to execute shell script, I can can simply invoke it via its relative or absolute path if the shell script file is executable. Thus I will have to make sure that the shell script file is executable

### Solution

I used the following commands one by one
```bash
./solve.sh
```
Upon execution, I got the flag
