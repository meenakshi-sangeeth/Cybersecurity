## Challenge

Let's dive into reverse engineering obfuscated code! This challenge is using VM-based obfuscation: reverse engineer the custom emulator and architecture to understand how to get the flag! If you are clever, you won't need to reverse too much VM code.

## Solution

```bash
hacker@reverse-engineering~trust-the-yancode-easy:~$ cd /challenge
hacker@reverse-engineering~trust-the-yancode-easy:/challenge$ ls -la
total 32
drwxr-xr-x 1 root root  4096 Oct 26 11:19 .
drwxr-xr-x 1 root root  4096 Oct 26 11:19 ..
-rwsr-xr-x 1 root root 22104 Sep 12 13:21 trust-the-yancode-easy
hacker@reverse-engineering~trust-the-yancode-easy:/challenge$ ./ trust-the-yancode-easy
bash: ./: Is a directory
hacker@reverse-engineering~trust-the-yancode-easy:/challenge$ ./trust-the-yancode-easy
[+] Welcome to ./trust-the-yancode-easy!
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
[s] IMM b = 0x7f
[s] IMM c = 0x4
[s] IMM a = 0
[s] SYS 0x4 a
[s] ... read_memory
flag
[s] ... return value (in register a): 0x4
[s] IMM b = 0x9f
[s] IMM c = 0x1
[s] IMM a = 0x2b
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xfa
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x6b
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xd9
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x1
[s] IMM b = 0
[s] IMM c = 0x1
[s] IMM d = 0x49
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
I[s] ... return value (in register a): 0x1
[s] IMM d = 0x4e
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
N[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x4f
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
O[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x45
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
E[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x54
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
T[s] ... return value (in register a): 0x1
[s] IMM d = 0x21
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
![s] ... return value (in register a): 0x1
[s] IMM a = 0x1
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write

[s] ... return value (in register a): 0x1
[s] SYS 0x20 a
[s] ... exit
hacker@reverse-engineering~trust-the-yancode-easy:/challenge$ 
hacker@reverse-engineering~trust-the-yancode-easy:/challenge$ echo -ne '\x2b\xfa\x6b\xd9' | ./trust-the-yancode-easy
[+] Welcome to ./trust-the-yancode-easy!
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
[s] IMM b = 0x7f
[s] IMM c = 0x4
[s] IMM a = 0
[s] SYS 0x4 a
[s] ... read_memory
[s] ... return value (in register a): 0x4
[s] IMM b = 0x9f
[s] IMM c = 0x1
[s] IMM a = 0x2b
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xfa
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x6b
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0xd9
[s] STM *b = a
[s] ADD b c
[s] IMM a = 0x1
[s] IMM b = 0
[s] IMM c = 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x4f
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
O[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x52
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
R[s] ... return value (in register a): 0x1
[s] IMM d = 0x45
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
E[s] ... return value (in register a): 0x1
[s] IMM d = 0x43
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
C[s] ... return value (in register a): 0x1
[s] IMM d = 0x54
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
T[s] ... return value (in register a): 0x1
[s] IMM d = 0x21
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
![s] ... return value (in register a): 0x1
[s] IMM d = 0x20
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
 [s] ... return value (in register a): 0x1
[s] IMM d = 0x59
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
Y[s] ... return value (in register a): 0x1
[s] IMM d = 0x6f
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
o[s] ... return value (in register a): 0x1
[s] IMM d = 0x75
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
u[s] ... return value (in register a): 0x1
[s] IMM d = 0x72
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
r[s] ... return value (in register a): 0x1
[s] IMM d = 0x20
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
 [s] ... return value (in register a): 0x1
[s] IMM d = 0x66
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
f[s] ... return value (in register a): 0x1
[s] IMM d = 0x6c
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
l[s] ... return value (in register a): 0x1
[s] IMM d = 0x61
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
a[s] ... return value (in register a): 0x1
[s] IMM d = 0x67
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
g[s] ... return value (in register a): 0x1
[s] IMM d = 0x3a
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
:[s] ... return value (in register a): 0x1
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x10 a
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
[s] SYS 0x8 a
[s] ... open
[s] ... return value (in register a): 0x3
[s] IMM c = 0x64
[s] SYS 0x4 c
[s] ... read_memory
[s] ... return value (in register c): 0x39
[s] IMM a = 0x1
[s] SYS 0x10 c
[s] ... write
pwn.college{0N7d4FjV172U2Rr2sVR8kwAot2n.01M3IDLyMjN0czW}
[s] ... return value (in register c): 0x39
[s] IMM a = 0
[s] IMM d = 0xa
[s] STM *b = d
[s] SYS 0x10 a
[s] ... write
[s] ... return value (in register a): 0xff
[s] SYS 0x20 a
[s] ... exit
```
