
### Challenge

To collect the flag by running `/challenge/run` after changing your directory to `/challenge`, using `?` glob instead of c and l in the argument to `cd` 

### Thought Process

I knew that when `?` character is encountered in any argument, the shell will treat it as single-character wildcard and try to replace that argument with any files matching that single character 

### Solution

I used the following commands
```bash
cd /?ha??enge
```
Upon execution, the directory was changed to `/challenge`. After that I used the following command
```bash
/challenge/run
```
Upon execution, I got the flag
