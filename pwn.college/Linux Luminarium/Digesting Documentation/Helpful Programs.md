### Challenge

To collect the flag by using `--help` 

### Thought Process

Since the challenge rewuired the usage of `--help`, I figured I'll have to pass `--help` to `/challenge/challenge`. I recalled that some programs don't have a man page, but might tell you how to run them if invoked with `--help`, often used as `-h` or, in rare cases, `-?`, `help`, or other esoteric values like `/?`

### Solution

I used the following command
```bash
/challenge/challenge --help
```
Upon execution, I got the following output
```bash
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
From the optional arguments, I figured I must pass `-p` and `-g` as the arguments to `/challenge/challenge` and hence I used the command `/challenge/challenge -p` which generated the following output
```bash
The secret value is: 981
```
Thus I used the following command
```bash
/challenge/challenge -g 981
```
Upon execution, I got the flag
