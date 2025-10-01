### Challenge

To collect the flag by running `/challenge/run` after creating a `/tmp/flag_fifo` file and redirect the stdout of `/challenge/run` to it

### Thought Process

Since it'll be hard to solve this challenge in a single terminal due to the blocking behavior of FIFOs, I'll gave to use two terminals. In the first terminal, I'll create the FIFO using `mkfifo` command and read it, while from the second terminal I'll redirect the output of `/challenge/run` 

### Solution

Terminal 1
```bash
~$ mkfifo /tmp/flag_fifo
~$ cat /tmp/flag_fifo
```

After this I opened another terminal

Terminal 2
```bash
~$ /challenge/run > /tmp/flag_fifo
```

I got the flag in terminal 1
