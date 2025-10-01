# Data Manipulation

## 1. Translating Characters

### Challenge

To collect the flag, run `/challenge/run`, but it prints the flag with swapped letter cases

### Thought Process

`tr` is a command which translates the character provided in its first argument to the character provided in its second argument. It can also handle multiple characters, with the characters in different positions of the first argument replaced with associated characters in the second argument.

### Solution

```bash
/challenge/run | tr 'A-Za-z' 'a-zA-Z'
```

## 2. Deleting Characters

### Challenge

To collect the flag, run `/challenge/run`, but it has some decoy characters like ^ and %

### Thought Process

To get the correct flag, I'll have to delete the decoy characters. For that, `tr` can be used with `-d` and an argument of what characters to delete

### Solution

```bash
/challenge/run | tr -d ^%
```

## 3. Deleting Newlines

### Challenge

To collect the flag, run `/challenge/run`, but it has a bunch of newlines 

### Thought Process

To get the correct flag, I'll have to delete the newlines. For that, `tr` can be used with `-d` and `\n` which is the standin for newline as the argument 

### Solution

```bash
/challenge/run | tr -d "\n"
```

## 4. Extracting the first lines with head 

### Challenge

To collect the flag, pipe the first 7 lines of `/challenge/pwn` into `/challenge/college`

### Thought Process

To get the first 7 lines, `/challenge/pwn` can be piped with `head`. It's a command used to display the first few lines of its input

### Solution

```bash
/challenge/pwn | head -n 7 | /challenge/college
```

## 5. Extracting specific sections of text 

### Challenge

To collect the flag, run `/challenge/run`, extract the second column and join them into a single line

### Thought Process

To extract the second column, `cut` command can be used with `-d` argument which specifies the column delimiter and `-f` argument which specifies the field number

### Solution

```bash
/challenge/run | cut -d " " -f 2 | tr -d "\n"
```

## 6. Sorting Data

### Challenge

To collect the flag from `/challenge/flags.txt` containing 100 fake flags, with the real flag mixed among them which will be at the end when sorted alphabetically

### Thought Process

To get the flag, first I'll have to sort the flags in reverse order and output the first flag which will be the real one. To sort the flag, `sort` command can be used which by default will sort them in alphabetic order. So, `-r` should be used as an argument to sort the lines in reverse order

### Solution

```bash
sort -r /challenge/flags.txt | head -n 1
```

