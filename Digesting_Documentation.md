# Digesting Documentation

## 1. Learning From Documentation

### Challenge

To collect the flag by invoking `/challenge/challenge` program with the argument `--giveflag`

### Thought Process

The task required me to run`/challenge/challenge` with athe argument `--giveflag`. I recalled that arguments are additional datas passed to the command and its syntax is command followed by an argument.

### Solution

I used the following command
```bash
/challenge/challenge --giveflag
```
Upon execution, I got the flag

## 2. Learning Complex Usage

### Challenge

To collect the flag by invoking `/challenge/challenge` program with the argument `--printfile`

### Thought Process

I knew that `--printfile` argument prints arbitrary files to the terminal and the argument to the --printfile argument is the path of the flag to read.

### Solution

I used the following command
```bash
/challenge/challenge --printfile /flag
```
Upon execution, I got the flag

## 3. Reading Manuals

### Challenge

To collect the flag by using a secret option which will be displayed through the man page for `challenge`

### Thought Process

I knew that man is short for manual, and will display (if available) the manual of the command you pass as an argument. I recalled that I can scroll around the manpage with arrow keys and PgUp/PgDn and when I'm done reading the manpage, I can hit 'q' to quit

### Solution

To display the manpage, I used the following command
```bash
man challenge
```
Upon execution, I got the following output
```bash
CHALLENGE(1)                                                                            Challenge Commands                                                                           CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --vhjuka NUM
              print the flag if NUM is 591
```
Thus I figured I'll have to run `/challenge/challenge` along with the the argument `--vhjuka 591`
```bash
/challenge/challenge --vhjuka 591
```
Upon execution, I got the flag

## 4. Searching Manuals

### Challenge

To collect the flag by reading the `challenge` man page and finding the option that will give the flag

### Thought Process

I knew that man is short for manual, and will display (if available) the manual of the command you pass as an argument. I recalled that I can search through the manpage by hitting *n* to go to the next result and *N* to go to the previous result

### Solution

To display the manpage, I used the following command
```bash
man challenge
```
Upon execution, I got the manpage comprising of a large number of lines. I figured I'll have to search through the manpage in order to find the right argument. I tried hitting *n* and the part of lines containing "flag" were highlighted. Thus I kept hitting *n* until I found the following line
![--tg   This argument will give you the flag!](data:image/png;base64,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)
Then I used the following command
```bash
/challenge/challenge --tg
```
Upon execution, I got the flag
