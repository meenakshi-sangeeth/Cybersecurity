### Challenge

To collect the flag which is hidden using the following instructions:
1. Your first clue is in /. Head on over there.
2. Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
3. cat that file to read the clue!
4. Depending on what the clue says, head on over to the next directory (or don't!).
5. Follow the clues to the flag!

### Thought Process

I knew that I'll have to navigate to `/` using cd after which I'll have to list the files using `ls`. Then I'll have to read the file which is named something along the lines of HINT or CLUE using `cat` command

### Solution

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
