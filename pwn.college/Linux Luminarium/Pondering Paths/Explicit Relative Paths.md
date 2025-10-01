### Challenge

To collect the flag by running `challenge/run` using `.` in the relative path while having a current working directory of `/`

### Thought Process

I knew that `.` represents the current directory and relative path is based on the current working directory (cwd) and doesn’t start with `/`. It was mentioned that cwd is `/`. So I would have to navigate to the root directory using the command `cd /`. Since the challenge was to run `challenge/run` using `.` in the relative path, I would have to prepend `./` to the relative path `challenge/run`.

### Solution

I navigated to the cwd using the command
```bash
cd /
```
After that I used the following command 
```bash
./challenge/run
```
Upon execution, I got the flag
