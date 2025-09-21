# Shell Variables 

## 1. Printing Variables

### Challenge

To collect the flag by printing out the FLAG variable

### Thought Process

I knew that when variables can be printed out with the command `echo`, by prepending the variable name with a `$`

### Solution

I used the following command
```bash
echo $FLAG
```
Upon execution, I got the flag

## 2. Setting Variables

### Challenge

To collect the flag by setting the PWN variable to the value COLLEGE 

### Thought Process

I knew that variables can be set to a value using `=`. I had to make sure that there are no spaces around the `=` because if there are spaces, the shell won't recognize a variable assignment

### Solution

I used the following command
```bash
PWN=COLLEGE
```
Upon execution, I got the flag

## 3. Multi-Word Variables

### Challenge

To collect the flag by setting the variable PWN to COLLEGE YEAH

### Thought Process

I knew that when the shell sees a space, it ends the variable assignment and interprets the next word as a command. Thus if I have to assign a value with space in between, I'll have to enclose the value in double quotes (")

### Solution

I used the following command
```bash
PWN="COLLEGE YEAH"
```
Upon execution, I got the flag

## 4. Exporting Variables

### Challenge

To collect the flag by invoking `/challenge/run` with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported

### Thought Process

I knew that variables that you set in a shell session are local to that shell process and thus if I have to export them, I'll have to use `export` before the variable that needs to be exported

### Solution

I used the following commands one by one
```bash
PWN=COLLEGE
export PWN
COLLEGE=PWN
/challenge/run
```
Upon execution, I got the flag

## 5. Printing Exported Variables

### Challenge

To collect the flag by finding the FLAG variable using the `env` command

### Thought Process

I knew that `env` will print out every exported variable set in your shell and thus if I search through the output after executing `env` command I'll be able to find the FLAG variable

### Solution

I used the following command
```bash
env
```
Upon execution, I got a list of exported variables from which I got the flag

## 6. Storing Command Output

### Challenge

To collect the flag by reading the output of the `/challenge/run` command directly into a variable called PWN

### Thought Process

I recalled that if I want to store the output of some command into a variable command substitution has to be used. It can be done by enclosing the command in the brackets of `$()`

### Solution

I used the following commands
```bash
PWN=$( /challenge/run)
echo $PWN
```
Upon execution, I got the flag

## 7. Reading Input

### Challenge

To collect the flag by setting the PWN variable to the value COLLEGE using `read`

### Thought Process

I knew that `read` is used when you have to set a variable to a value inputted by the user. It can be done by executing `read` followed by the variable name

### Solution

I used the following command
```bash
read PWN
```
After execution, I entered COLLEGE into the terminal which gave me the flag

## 7. Reading Files

### Challenge

To collect the flag by reading `/challenge/read_me` into the PWN environment variable with a single command as `/challenge/read_me` will keep changing

### Thought Process

I recalled that I can read user input into a variable using `read` and I can  redirect files into command input using `<`. Thus if I use both of these together in a single command I'll be able to complete the challenge

### Solution

I used the following command
```bash
read PWN < /challenge/read_me
```
After execution, I got the flag

