### Challenge

To collect the flag by running `/challenge/run` using a relative path while having a current working directory of `/`

### Thought Process

I knew that relative path is based on the current working directory (cwd) and doesn’t start with `/`. It was mentioned that cwd is `/`. So I would have to navigate to the root directory using the command `cd /`. Since the challenge was to run `/challenge/run` using a relative path, I needed to figure out the path from `/` to the `run` file. A hint was given that said the relative path starts with the letter "c". Thus I figured that the file is most likely to be in the `challenge` folder and knowing that `/challenge/run` is an absolute path, I would have to remove the leading `/`, so that the relative path would become `challenge/run`.

### Solution

I navigated to the cwd using the command
```bash
cd /
```
After that I used the following command 
```bash
challenge/run
```
Upon execution, I got the flag
