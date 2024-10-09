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

![Image](cryptonite_taskphase_meenakshi/Screenshot 2024-10-09 173014.png)


Then I used the following command
```bash
/challenge/challenge --tg
```
Upon execution, I got the flag
