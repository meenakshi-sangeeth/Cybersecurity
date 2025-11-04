## Challenge

Let's continue deeper in reverse engineering obfuscated code! This challenge is using VM-based obfuscation: reverse engineer the custom emulator and architecture to understand how to get the flag!

## Solution

```bash
hacker@reverse-engineering~know-the-yancode-easy:~$ cd /challenge
hacker@reverse-engineering~know-the-yancode-easy:/challenge$ ls -la
total 32
drwxr-xr-x 1 root root  4096 Oct 26 11:30 .
drwxr-xr-x 1 root root  4096 Oct 26 11:30 ..
-rwsr-xr-x 1 root root 22064 Sep 12 13:21 know-the-yancode-easy
hacker@reverse-engineering~know-the-yancode-easy:/challenge$ ./know-the-yancode-easy
[+] Welcome to ./know-the-yancode-easy!
[+] This challenge is an custom emulator. It emulates a completely custom
[+] architecture that we call "Yan85"! You'll have to understand the
[+] emulator to understand the architecture, and you'll have to understand
[+] the architecture to understand the code being emulated, and you will
[+] have to understand that code to get the flag. Good luck!
[+]
[+] This is an introductory Yan85 level, where we trigger Yan85 architecture
[+] operations directly. The parts of Yan85 that are used here is the emulated
[+] registers, memory, and system calls.
[+]
[+] This is a *teaching* challenge, which means that it will output
[+] a trace of the Yan85 code as it processes it. The output is here
[+] for you to understand what the challenge is doing, and you should use
[+] it as a guide to help with your reversing of the code.
[+]
[s] IMM b = 0x75
[s] IMM c = 0x4
[s] IMM a = 0
[s] SYS 0x4 a
[s] ... read_memory

[s] ... return value (in register a): 0x1
[s] IMM b = 0x95
[s] IMM c = 0x1
[s] IMM a = 0xdd
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x3f
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xc1
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x51
[s] STM *b = a
[s] ADD b c
[s] IMM b = 0x95
[s] LDM b = *b
[s] IMM a = 0x75
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x96
[s] LDM b = *b
[s] IMM a = 0x76
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x97
[s] LDM b = *b
[s] IMM a = 0x77
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x98
[s] LDM b = *b
[s] IMM a = 0x78
[s] LDM a = *a
[s] CMP a b
[s] IMM a = 0x1
[s] IMM b = 0
[s] IMM c = 0x1
[s] IMM d = 0x49
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
I[s] ... return value (in register a): 0x1
[s] IMM d = 0x4e
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
N[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x4f
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
O[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x45
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
E[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x54
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
T[s] ... return value (in register a): 0x1
[s] IMM d = 0x21
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
![s] ... return value (in register a): 0x1
[s] IMM a = 0x1
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write

[s] ... return value (in register a): 0x1
[s] SYS 0x10 a
[s] ... exit
hacker@reverse-engineering~know-the-yancode-easy:/challenge$ echo -ne '\xdd\x3f\xc1\x51' | ./know-the-yancode-easy
[+] Welcome to ./know-the-yancode-easy!
[+] This challenge is an custom emulator. It emulates a completely custom
[+] architecture that we call "Yan85"! You'll have to understand the
[+] emulator to understand the architecture, and you'll have to understand
[+] the architecture to understand the code being emulated, and you will
[+] have to understand that code to get the flag. Good luck!
[+]
[+] This is an introductory Yan85 level, where we trigger Yan85 architecture
[+] operations directly. The parts of Yan85 that are used here is the emulated
[+] registers, memory, and system calls.
[+]
[+] This is a *teaching* challenge, which means that it will output
[+] a trace of the Yan85 code as it processes it. The output is here
[+] for you to understand what the challenge is doing, and you should use
[+] it as a guide to help with your reversing of the code.
[+]
[s] IMM b = 0x75
[s] IMM c = 0x4
[s] IMM a = 0
[s] SYS 0x4 a
[s] ... read_memory
[s] ... return value (in register a): 0x4
[s] IMM b = 0x95
[s] IMM c = 0x1
[s] IMM a = 0xdd
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x3f
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xc1
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x51
[s] STM *b = a
[s] ADD b c
[s] IMM b = 0x95
[s] LDM b = *b
[s] IMM a = 0x75
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x96
[s] LDM b = *b
[s] IMM a = 0x76
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x97
[s] LDM b = *b
[s] IMM a = 0x77
[s] LDM a = *a
[s] CMP a b
[s] IMM b = 0x98
[s] LDM b = *b
[s] IMM a = 0x78
[s] LDM a = *a
[s] CMP a b
[s] IMM a = 0x1
[s] IMM b = 0
[s] IMM c = 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x4f
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
O[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x45
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
E[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x54
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
T[s] ... return value (in register a): 0x1
[s] IMM d = 0x21
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
![s] ... return value (in register a): 0x1
[s] IMM d = 0x20
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
 [s] ... return value (in register a): 0x1
[s] IMM d = 0x59
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
Y[s] ... return value (in register a): 0x1
[s] IMM d = 0x6f
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
o[s] ... return value (in register a): 0x1
[s] IMM d = 0x75
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
u[s] ... return value (in register a): 0x1
[s] IMM d = 0x72
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
r[s] ... return value (in register a): 0x1
[s] IMM d = 0x20
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
 [s] ... return value (in register a): 0x1
[s] IMM d = 0x66
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
f[s] ... return value (in register a): 0x1
[s] IMM d = 0x6c
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
l[s] ... return value (in register a): 0x1
[s] IMM d = 0x61
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
a[s] ... return value (in register a): 0x1
[s] IMM d = 0x67
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
g[s] ... return value (in register a): 0x1
[s] IMM d = 0x3a
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
:[s] ... return value (in register a): 0x1
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write

[s] ... return value (in register a): 0x1
[s] IMM d = 0x2f
[s] IMM b = 0
[s] STM *b = d
[s] IMM d = 0x66
[s] IMM b = 0x1
[s] STM *b = d
[s] IMM d = 0x6c
[s] IMM b = 0x2
[s] STM *b = d
[s] IMM d = 0x61
[s] IMM b = 0x3
[s] STM *b = d
[s] IMM d = 0x67
[s] IMM b = 0x4
[s] STM *b = d
[s] IMM d = 0
[s] IMM b = 0x5
[s] STM *b = d
[s] IMM a = 0
[s] IMM b = 0
[s] SYS 0x20 a
[s] ... open
[s] ... return value (in register a): 0x3
[s] IMM c = 0x64
[s] SYS 0x4 c
[s] ... read_memory
[s] ... return value (in register c): 0x39
[s] IMM a = 0x1
[s] SYS 0x2 c
[s] ... write
pwn.college{AB4rjzjY4nmQPZC5MPkMDpVFKFs.0VN3IDLyMjN0czW}
[s] ... return value (in register c): 0x39
[s] IMM a = 0
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x2 a
[s] ... write
[s] ... return value (in register a): 0xff
[s] SYS 0x10 a
[s] ... exit
```
