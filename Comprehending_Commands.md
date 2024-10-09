# Comprehending Commands

## 1. Cat: Not The Pet, But The Command!

### Challenge

To collect the flag by reading the flag file using `cat` command

### Thought Process

I knew that `cat` command will read the contents from the file given as the argument

### Solution

I used the following command
```bash
cat flag
```
Upon execution, I got the flag

## 2. Catting Absolute Paths

### Challenge

To collect the flag by reading the flag file by its absolute path `/flag` using `cat` command 

### Thought Process

I knew that `cat` command will read the contents from the file given as the argument

### Solution

I used the following command
```bash
cat /flag
```
Upon execution, I got the flag

## 3. More Catting Practice

### Challenge

To collect the flag by reading the flag file by its absolute path without using the `cd` command

### Thought Process

In the terminal it was shown that the location of the flag file is `/usr/include/bsd/flag`. I knew that if I give the given file path as the argument to `cat` command, the contents of the file will be read without using `cd` command 

### Solution

I used the following command
```bash
cat /usr/include/bsd/flag
```
Upon execution, I got the flag

## 4. Grepping For A Needle In A Haystack

### Challenge

To collect the flag by reading the file `/challenge/data.txt` using `grep` command

### Thought Process

I knew that grep will search the file for lines of text containing the argument and print them to the console. It was given as a hint that flag always starts with the text pwn.college. Thus I figured that I'll have to pass pwn.college as the argument

### Solution

I used the following command
```bash
grep pwn.college /challenge/data.txt
```
Upon execution, I got the flag

## 5. Listing Files

### Challenge

To collect the flag by listing the files in /challenge

### Thought Process

I knew that `ls` command will list all the files in the directory provided to it as argument. 

### Solution

I used the following command
```bash
ls /challenge
```
Upon execution, I got the following ouptut
```bash
hacker@commands-listing-files:~$ ls /challenge
15153-renamed-run-4699 DESCRIPTION.md
```
I figured that the flag will be in `15153-renamed-run-4699` since it was mentioned that `/challenge/run` is renamed with some random name. Thus I used the following command
```bash
/challenge/15153-renamed-run-4699 
```
Upon execution, I got the flag

## 6. Touching Files

### Challenge

To collect the flag by creating two files `/tmp/pwn` and `/tmp/college`, and running `/challenge/run`

### Thought Process

I knew that `touch` command will create files

### Solution

I used the following commands
```bash
touch /tmp/pwn
touch /tmp/college
/challenge/run
```
Upon execution, I got the flag

## 7. Removing Files

### Challenge

To collect the flag by deleting `delete_me` file from home directory and running `/challenge/check`

### Thought Process

I knew that `rm` command will remove files

### Solution

I used the following commands
```bash
rm delete_me
/challenge/check
```
Upon execution, I got the flag

## 8. Hidden Files

### Challenge

To collect the flag which is hidden as a dot-prepended file in /.

### Thought Process

I knew that Linux has a convention where files that start with a `.` don't show up by default in `ls` and to view them with ls, you need to invoke ls with the `-a` flag

### Solution

I used the following commands
```bash
cd /
ls -a
```
Upon execution, I got the list of files in which `.flag-184822641918524` was mentioned. Thus I used the following command
```bash
cat .flag-184822641918524
```
Upon exection, I got the flag

## 9. An Epic File System Quest

### Challenge

To collect the flag which is hidden using the following instructions:
1. Your first clue is in /. Head on over there.
2. Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
3. cat that file to read the clue!
4. Depending on what the clue says, head on over to the next directory (or don't!).
5. Follow the clues to the flag!

### Thought Process

I knew that I'll have to navigate to `/` using cd after which I'll have to list the files using `ls`. Then I'll have to read the file which is named something along the lines of HINT or CLUE using `cat` command

###Solution

I used the following commands
```bash
cd /
ls 
```
Upon execution, I got the list of files in which `WHISPER` was mentioned. I figured that the clue will be in it and thus I used the following command
```bash
cat WHISPER
```
Upon exection, I got the next clue. After a series of such clues which were found using the commands `cat`, `ls` and `ls -a`, I got the flag

## 10. Making Directories

### Challenge

To collect the flag by running `/challenge/run` after creating a `/tmp/pwn` directory and making a `college` file within it

### Thought Process

I knew that directories can be created using the `mkdir` command and files using `touch` command

### Solution

I used the following commands
```bash
mkdir /tmp/pwn
touch /tmp/pwn/college
/challenge/run
```
Upon exection, I got the flag

## 11. Finding Files

### Challenge

To collect the flag which is hidden in a random directory on the filesystem

### Thought Process

I knew that the whole filesystem can be searched using `find / -name` command

### Solution

I used the following commands
```bash
find / -name flag
```
Upon exection, I got a list of files among which plenty of them were not accessible to normal user and it was mentioned that flag won't be hidden in such files. Thus I figured I'll have to read the contents of the accessible files using `cat` command. After a series of trial and error, I got the flag

## 12. Linking Files

### Challenge

To collect the flag which is in `/flag`, but `/challenge/catflag` will instead read out `/home/hacker/not-the-flag` thereby requiring the use of symlink

### Thought Process

I knew that symbolic links are created with the ln command with the -s argument where the original file path comes before the link path in the command

### Solution

I used the following commands
```bash
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag
```
Upon exection, I got the flag







