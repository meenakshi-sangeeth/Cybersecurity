### Challenge

To collect the flag by retrieving the exit code returned by `/challenge/get-code` and then running `/challenge/submit-code` with that error code as an argument

### Thought Process

I knew that the exit code of the most recently-terminated command can be accessed using the special `?` variable. I had to make sure that I prepend the variable with `$` to read its value

### Solution

I used the following command
```bash
 /challenge/get-code
```
Upon execution, I got an output saying `Exiting with an error code!` after which I used `echo $?` which gave `38` as the output. 
Thus, I used the following command
```bash
/challenge/submit-code 38
```
Upon execution, I got the flag

