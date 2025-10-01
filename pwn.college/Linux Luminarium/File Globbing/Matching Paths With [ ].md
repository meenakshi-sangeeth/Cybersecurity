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
