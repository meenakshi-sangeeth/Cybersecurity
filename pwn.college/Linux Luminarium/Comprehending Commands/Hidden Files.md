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
