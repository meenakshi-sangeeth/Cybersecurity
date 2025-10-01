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
