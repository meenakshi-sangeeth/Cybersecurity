
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
