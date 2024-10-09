# Practising Piping

## 1. Redirecting Output

### Challenge

To collect the flag by writing the word PWN to the filename COLLEGE using `>`

### Thought Process

I knew that `>` is used to redirect stdout to files. Thus if I use `>` between `echo PWN` and `COLLEGE`, I'll be able to complete the challenge

### Solution

I used the following command
```bash
echo PWN > COLLEGE
```
Upon execution, I got the flag

## 2. Redirecting More Output

### Challenge

To collect the flag after redirecting the output of `/challenge/run` to the file `myflag`

### Thought Process

I knew that `>` can be used to redirect the output of any command. Thus if I use `>` between `/challenge/run` and `myflag`, I'll be able to redirect the output as the challenge requires

### Solution

I used the following commands
```bash
/challenge/run > myflag
cat myflag
```
Upon execution, I got the flag

## 2. Appending Output

### Challenge

To collect the flag by running `/challenge/run` with an append-mode redirect of the output to the file /home/hacker/the-flag

### Thought Process

I knew that `>>` should be used if I want the output of a bunch of commands to keep appending to the same file since `>` will create a new output file every time, deleting the old contents

### Solution

I used the following commands
```bash
 /challenge/run >> /home/hacker/the-flag
cat /home/hacker/the-flag
```
Upon execution, I got the flag

## 3. Redirecting Error

### Challenge

To collect the flag by redirecting the output of `/challenge/run`, to `myflag` and the errors  to `instructions`

### Thought Process

I knew that if there's a command that might produce data via standard error, I  can redirect standard error (FD 2) to the a file using `2>` between the command and the file

### Solution

I used the following commands
```bash
/challenge/run > myflag 2> instructions
cat myflag
```
Upon execution, I got the flag

## 4. Redirecting Input

### Challenge

To collect the flag by redirecting the PWN file to `/challenge/run` and have the PWN file contain the value COLLEGE

### Thought Process

I knew that I can redirect input to programs using `<` and I recalled that for output redirection I'll have to use `>`. Thus for the PWN file to contain COLLEGE I'll have to use `>` and to redirect PWN file to `/challenge/run`, I'll have to use `<`

### Solution

I used the following commands
```bash
echo COLLEGE > PWN
/challenge/run < PWN
```
Upon execution, I got the flag

## 5. Grepping Stored Results

### Challenge

To collect the flag by following the given instructions:
1. Redirect the output of `/challenge/run` to `/tmp/data.txt`
2. This will result in a hundred thousand lines of text, with one of them being the flag, in `/tmp/data.txt`
3. Grep that for the flag!

### Thought Process

I knew that redirecting of the output can be done using `>` and searching through the resulting file using `grep`

### Solution

I used the following command
```bash
/challenge/run > /tmp/data.txt
```
As mentioned in the challenge, the execution of the above command lead to an output of hundred thousand lines of text, through which I searched for the flag using the following command
```bash
grep "pwn.college" /tmp/data.txt
```
Upon execution, I got the flag

## 6. Grepping Live Output

### Challenge

To collect the flag by grepping for it after running `/challenge/run` using pipe operator

### Thought Process

I knew that standard output from the command to the left of the pipe operator will be connected to (piped into) the standard input of the command to the right of the pipe. Thus if I use `|` (pipe) operator between `/challenge/run` and `grep` I'll be able to meet the requirements of the challenge

### Solution

I used the following command
```bash
/challenge/run | grep pwn.college 
```
Upon execution, I got the flag

## 7. Grepping Errors

### Challenge

To collect the flag by grepping through the errors after running `/challenge/run` using pipe operator

### Thought Process

I recalled that if I have to grep through errors, first, I'll have to redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)

### Solution

I used the following command
```bash
/challenge/run 2>&1 | grep "pwn.college"
```
Upon execution, I got the flag

## 8. Duplicating Piped Data With Tee

### Challenge

To collect the flag by piping `/challenge/pwn` into `/challenge/college` after intercepting the data to see what pwn needs from you

### Thought Process

I knew that `tee` command duplicates data flowing through your pipes to any number of files provided on the command line. Thus for intercepting the data I'll have to use `tee`

### Solution

I used the following command
```bash
/challenge/pwn | tee code | /challenge/college
cat code
```
Upon execution, I got the following output
```bash
Usage: /challenge/pwn-secret [SECRET_ARG]
SECRET_ARG should be "kNkC3zyg"
```
Thus I used the following command
```bash
/challenge/pwn--secret kNkC3zyg | /challenge/college
```
Upon execution, I got the flag

## 9. Writing To Multiple Programs

### Challenge

To collect the flag by running `/challenge/hack` and duplicating its output as input to both the `/challenge/the` and the `/challenge/planet` commands

### Thought Process

In order to duplicate the output of `/challenge/hack` into both `/challenge/the` and the `/challenge/planet` , I knew I would have to make use of process substitution with the command `tee`

### Solution

I used the following command
```bash
/challenge/hack | tee >( /challenge/the ) >( /challenge/planet )
```
Upon execution, I got the flag

## 10. Split - Piping Stderr And Stdout

### Challenge

To collect the flag by combining the usage of `>()`, `2>`, and `|` with the following:
- `/challenge/hack`: this produces data on stdout and stderr
- `/challenge/the`: you must redirect hack's stderr to this program
- `/challenge/planet`: you must redirect hack's stdout to this program

### Thought Process

In order to redirect stderr of `/challenge/hack` to I'll have to use `2>` as well as process substitution `>()` to feed the `stderr` output into `/challenge/the`. After that `|` operator should be used to pipe stdout of `/challenge/hack` into `/challenge/planet`

### Solution

I used the following command
```bash
/challenge/hack 2> >( /challenge/the ) | /challenge/planet
```
Upon execution, I got the flag
