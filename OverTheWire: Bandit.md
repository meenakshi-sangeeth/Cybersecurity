## Level 0 -> Level 1

`cat readme`

## Level 1 -> Level 2

`cat ./-`

## Level 2 -> Level 3

`cat "spaces in this filename"`

## Level 3 -> Level 4

```bash
cd inhere
ls -a
cat ...Hiding-From-You
```

## Level 4 -> Level 5

```bash
ls
cd inhere
ls
cat ./-file07
```

## Level 5 -> Level 6

```bash
cd inhere
ls
find type fsize 1033c-executable
cat /maybehere07/.file2
```

## Level 6 -> Level 7

```bash
find / -type fuser bandit7-group bandit6 size 33c
cat /var/lib/dpkg/info/bandit7.password
```

## Level 7 -> Level 8

```bash
ls
grep "millionth" data.txt
```

## Level 8 -> Level 9

```bash
sort data.txt | unique -c
```

## Level 9 -> Level 10

```bash
strings data.txt | grep "="
```

## Level 10 -> Level 11
```bash
base 64 -d data.txt
```

## Level 11 -> Level 12
```bash
cat data.txt
```
Decoded the rot13 string using an online platform

## Level 12 -> Level 13
```bash
cat data.txt
mkdir /temp/overthewire
cp data.txt /temp/overthewire
cd /temp/overthewire
ls
xxd -r data.txt > data
ls
file data
mv data file.gz
gzip -d file.gz
ls
file file
mv file file.bz2
bzip2 -d file.bz2
ls
file file
mv file fie.gz
gzip -d file.gz
ls
file file
mv file file.tar
tar xf file.tar
ls
file data5.bin
mv data5.bin data.tar
tar xf data.tar
ls
file data6.bin
mv data6.bin data.bz2
bzip2 -d data.bz2
ls
file data
mv data data.tar
ls
tar xf data.tar
ls
file data8.bin
mv data8.bin data.gz
gzip -d data.gz
ls
file data
cat data
```
## Level 13 -> Level 14

```bash
ssh -i sshkey.private bandit14@localhost
cat /etc/bandit_pass/bandit14
```

## Level 14 -> Level 15

```bash
nc localhost 30000
```

## Level 15 -> Level 16

```bash
cat /etc/bandit_pass/bandit15
ncat --ssl localhost 30001
```

## Level 16 -> Level 17

```bash
cat /etc/bandit_pass/bandit16
nmap localhost -p31000-32000
nc localhost 31790
ncat --ssl localhost 31790
vim key
chmod 400 key
ssh -i key bandit17@localhost
```

## Level 17 -> Level 18

```bash
diff passwords.old passwords.new
```

## Level 18 -> Level 19

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh
ls
cat readme
```



