### Challenge

To collect the flag from two given files `/challenge/decoys_only.txt` and `/challenge/decoys_and_real.txt` which contains 100 fake flags and all 100 fake flags plus the one real flag respectively

### Thought Process

Since both the files contain 100 fake flags and only differ by the real flag, I can use `diff` to find the real flag. `diff` is a command which compares two files line by line and shows you exactly what's different between them

### Solution

```bash
diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
```
