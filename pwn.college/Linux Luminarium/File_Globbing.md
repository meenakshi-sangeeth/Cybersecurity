# File Globbing

## 1. Matching With *

### Challenge

To collect the flag by running `/challenge/run` after changing your directory to `/challenge`, using `*` glob to keep the argument you pass to `cd` to at most four characters

### Thought Process

I knew that when `*` character is encountered in any argument, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern. Thus if make use of `*`, I can limit the characters of argument to at most four

### Solution

I used the following command
```bash
cd /ch*
```
Upon execution, the directory was changed to `/challenge`. After that I used the following command
```bash
/challenge/run
```
Upon execution, I got the flag

## 2. Matching With ?

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

## 3. Matching With [ ]

### Challenge

To collect the flag by changing your working directory to `/challenge/files` and run `/challenge/run` with a single argument that bracket-globs into `file_b`, `file_a`, `file_s`, and `file_h`

### Thought Process

I knew that `[ ]` is a wildcard for a subset of potential characters, specified within the brackets. Thus if I specify "bash" within `[ ]` I'll be able to meet the requirements of the challenge since one character of all the mentioned files is present in "bash"

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run file_[bash]
```
Upon execution, I got the flag

## 4. Matching Paths With [ ]

### Challenge

To collect the flag by running `/challenge/run` from home directory with a single argument that bracket-globs into the absolute paths to the `file_b`, `file_a`, `file_s`, and `file_h` files placed in `/challenge/files`

### Thought Process

I recalled that globbing can happen on a path basis as well. So, I can expand entire paths with `[ ]` thereby meeting the requirement of the challenge. Since one character of all the mentioned files is present in "bash", I can use `[bash]`

### Solution

I used the following commands
```bash
/challenge/run /challenge/files/file_[bash]
```
Upon execution, I got the flag

## 5. Mixing Globs

### Challenge

To collect the flag by changing the directory to `/challenge/files` and write a single, short (6 characters or less) glob that will match the files "challenging", "educational", and "pwning"

### Thought Process

Since there's no common pattern of characters in the files mentioned, I figured I'll have to use a comination of `[ ]` and `*` globs and pass "cep" to `[ ]` which will meet the requirements of the challenge

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run [cep]*
```
Upon execution, I got the flag

## 6. Exclusionary Globbing

### Challenge

To collect the flag by running `/challenge/run` with all files that don't start with "p", "w", or "n" after changing your directory to `/challenge`

### Thought Process

I recalled that if the first character in the brackets is a `!` or (in newer versions of bash) a `^`, the glob inverts, and that bracket instance matches characters that aren't listed. Thus I figured I'll have to use `!` or `^` to match with the files that don't start with "p", "w", or "n"

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run [!pwn]*
```
Upon execution, I got the flag

## 7. Multiple Globs

### Challenge

To collect the flag by running `/challenge/run` in `/challenge/files`, providing a single argument of 3 characters or less, that covers every word that contains the letter p

### Thought Process

Bash supports the expansion of multiple globs in a single word. Thus I can use `*` glob before and after the letter p thereby covering every word containing the letter p

### Solution

I used the following commands
```bash
cd /challenge/files
/challenge/run *p*
```
Upon execution, I got the flag

## 8. Tab Completion

### Challenge

To collect the flag by reading `/challenge/pwncollege` using tab completion

### Thought Process

Files can be specified by entering <TAB> in the shell, which will try to figure out what you're going to type and automatically complete it

### Solution

```bash
cat /challenge/p<TAB>
```

## 9. Multiple Options for Tab Completion

### Challenge

To collect the flag using tab completion from `/challenge/files`, which has a bunch of files starting with `pwncollege`

### Thought Process

When there are multiple options for tab completion, by default bash will auto-expand until the first point. When you hit tab a second time, it'll print out those options

### Solution

```bash
~$ cat /challenge/p<TAB><TAB>
pwn                    pwncollege-family      pwncollege-flyswatter
pwn-college            pwncollege-flag        pwncollege-hacking
pwn-the-planet         pwncollege-flamingo
~$ cat /challenge/pwncollege-flag
```

## 10. Tab Completion on commands

### Challenge

To collect the flag by tab-completing a command that starts with `pwncollege`

### Thought Process

Commands can also be auto completed using the tab key just like for files

### Solution

```bash
pwncollege<TAB>
```

