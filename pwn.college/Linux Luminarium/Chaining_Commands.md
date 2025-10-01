# Chaining Commands

## 1. Chaining With Semicolons

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

## 2. Your First Shell Script

### Challenge

To collect the flag by creating a shell script called `x.sh`, and running it with `bash`

### Thought Process

I knew that a shell script created and executed after naming it with a `sh` suffix and then passing it as an argument to `bash`

### Solution

I used the following command
```bash
~$ echo '/challenge/pwn' > x.sh
~$ echo '/challenge/college' >> x.sh
~$ bash x.sh
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

I knew that instead of manually invoking `bash` to execute shell script, I  can simply invoke it via its relative or absolute path if the shell script file is executable. Thus I will have to make sure that the shell script file is executable

### Solution

I used the following commands one by one
```bash
./solve.sh
```
Upon execution, I got the flag

## 5. Building on Success

### Challenge

To collect the flag by chaining the programs `/challenge/first-success` and `/challenge/second` using the `&&` operator

### Solution

```bash
/challenge/first-success && /challenge/second
```
Upon execution, I got the flag

## 6. Handling Failure

### Challenge

To collect the flag by chaining the programs `/challenge/first-failure` and `/challenge/second` using the `||` operator

### Solution

I used the following commands one by one
```bash
/challenge/first-failure || /challenge/second
```

## 7. Understanding Shebangs 

### Challenge

To collect the flag by running `challenge/run` after creating an executable script at `/home/hacker/solve.sh` that has a proper shebang and outputs "hack the planet"

### Thought Process

A shebang is the `#!/bin/bash` line at the beginning of the script that tells the system which interpreter to use

### Solution

```bash
~$ echo '#!/bin/bash' > /home/hacker/solve.sh
~$ echo 'echo "hack the planet"' >> /home/hacker/solve.sh
~$ /challenge/run
```

## 8. Scripting with Arguments

### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes two arguments
- Outputs them in REVERSE order (second argument first, then the first argument)

### Thought Process

The first and second argument can be accessed by the script using special variables `$1` and `$2` respectively

### Solution

```bash
~$ echo '#!/bin/bash' > /home/hacker/solve.sh
~$ echo 'echo "$2 $1"' >> /home/hacker/solve.sh
~$ /challenge/run
```

## 9. Scripting with Conditionals

### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output nothing

### Thought Process

In bash, `if` statement can be used to make decisions. Thus I can check if the argument is "pwn" or not using `if` statement

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n  echo "college"\nfi' > /home/hacker/solve.sh 
~$ /challenge/run
```

## 10. Scripting with Defeault Cases

### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "pwn", output "college"
- For any other input, output "nope"

### Thought Process

In bash, `if` statement can be used to make decisions. Thus I can check if the argument is "pwn" or not using `if` statement and output "college" if it matches using `then`. Otherwise "nope" can be outputted using `else`

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "pwn" ]\nthen\n    echo "college"\nelse\n    echo "nope"\nfi' > /home/hacker/solve.sh
~$ /challenge/run
```

## 11. Scripting with Multiple Conditions

### Challenge

To collect the flag by writing a script at `/home/hacker/solve.sh` that
- Takes one argument
- If the argument is "hack", output "the planet"
- If the argument is "pwn", output "college"
- If the argument is "learn", output "linux"
- For any other input, output "unknown"

### Thought Process

In bash, multiple conditions can be checked using `elif`

### Solution

```bash
~$ echo -e '#!/bin/bash\nif [ "$1" == "hack" ]\nthen\n    echo "the planet"\nelif [ "$1" == "pwn" ]\nthen\n    echo "college"\nelif [ "$1" == "learn" ]\nthen\n    echo "linux"\nelse\n    echo "unknown"\nfi' > /home/hacker/solve.sh
~$ /challenge/run
```

## 12. Reading Shell Scripts

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


