### Challenge

To collect the flag by executing `run` program using a relative path while having a current working directory of `/challenge`

### Thought Process

First I would have to navigate to the cwd using the command `cd /challenge`.  I knew that simply executing the command `run` within `/challenge` directory will not invoke `/challenge/run` since Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. I also knew that `.` represents the current directory. Thus I figured I would have to prepend `./` to the command `run` within `/challenge` directory.

### Solution

I navigated to the cwd using the command
```bash
cd /challenge
```
After that I used the following command 
```bash
./run
```
Upon execution, I got the flag
