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
