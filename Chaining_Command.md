# Chaining Commands

## 1. Chaining WIth Semicolons

### Challenge

To collect the flag by running `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon

### Thought Process

I knew that `;` is used to chain commands. Basically, when you hit Enter, your shell executes your typed command and, after that command terminates, give you the prompt to input another command. The semicolon is analogous, just without the prompt and with you entering both commands before anything is executed

### Solution

I used the following command
```bash
/challenge/pwn; /challenge/college
```
Upon execution, I got the the flag

## 2.Your First Shell Script

### Challenge

To collect the flag by creating a shell script called `x.sh`, and running it with `bash`

### Thought Process

I knew that a shell script created and executed after naming it with a `sh` suffix and then passing it as an argument to `bash`

### Solution

I used the following command
```bash
bash x.sh
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
