# Pondering PATH

## 1. The PATH Variable

### Challenge

To collect the flag by disrupting the operation of the `/challenge/run` program in such a way that the program can't find the `rm` command since it delete the flag using `rm`

### Thought Process

I knew that there is a special shell variable, called `PATH`, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. Thus if I use `PATH`, I will be able to obtain the flag

### Solution

I used the following commands
```bash
PATH=""
/challenge/run
```
Upon execution, I got the the flag

## 2.Setting PATH

### Challenge

To collect the flag by overwriting `PATH` with `/challenge/more_commands/` directory

### Thought Process

I knew that `PATH` can be set to a new value or overwrite it using `=` since `PATH` is a variable

### Solution

I used the following commands
```bash
PATH=/challenge/more_commands/
/challenge/run
```
Upon execution, I recieved the flag

## 3. Redirecting Script Output

### Challenge

To collect the flag by piping the output of the script into a single invocation of the `/challenge/solve` command

### Thought Process

I recalled that `|` operator redirects standard output of one command to another. Thus I will have to use `|` operator to pipe the output of the script to `/challenge/solve`

### Solution

I used the following command
```bash
bash x.sh | /challenge/solve
```
Upon execution, I got the flag

## 4. Executable Shell Scripts

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
