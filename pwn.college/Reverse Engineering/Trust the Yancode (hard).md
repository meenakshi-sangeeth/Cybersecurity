## Challenge

Let's dive into reverse engineering obfuscated code! This challenge is using VM-based obfuscation: reverse engineer the custom emulator and architecture to understand how to get the flag! If you are clever, you won't need to reverse too much VM code.

## Solution

```bash
hacker@reverse-engineering~trust-the-yancode-hard:/challenge$ gdb ./trust-the-yancode-hard
GNU gdb (GDB) 16.2
Copyright (C) 2024 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-unknown-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
--Type <RET> for more, q to quit, c to continue without paging--c
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./trust-the-yancode-hard...
(No debugging symbols found in ./trust-the-yancode-hard)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x00000000000010d0  __cxa_finalize@plt
0x00000000000010e0  puts@plt
0x00000000000010f0  write@plt
0x0000000000001100  __stack_chk_fail@plt
0x0000000000001110  printf@plt
0x0000000000001120  read@plt
--Type <RET> for more, q to quit, c to continue without paging--c
0x0000000000001130  memcmp@plt
0x0000000000001140  setvbuf@plt
0x0000000000001150  open@plt
0x0000000000001160  exit@plt
0x0000000000001170  sleep@plt
(gdb) info file
Symbols from "/challenge/trust-the-yancode-hard".
Local exec file:
        `/challenge/trust-the-yancode-hard', file type elf64-x86-64.
        Entry point: 0x1180
        0x0000000000000318 - 0x0000000000000334 is .interp
        0x0000000000000338 - 0x0000000000000358 is .note.gnu.property
        0x0000000000000358 - 0x000000000000037c is .note.gnu.build-id
        0x000000000000037c - 0x000000000000039c is .note.ABI-tag
        0x00000000000003a0 - 0x00000000000003c8 is .gnu.hash
--Type <RET> for more, q to quit, c to continue without paging--c
        0x00000000000003c8 - 0x0000000000000560 is .dynsym
        0x0000000000000560 - 0x0000000000000635 is .dynstr
        0x0000000000000636 - 0x0000000000000658 is .gnu.version
        0x0000000000000658 - 0x0000000000000688 is .gnu.version_r
        0x0000000000000688 - 0x0000000000000760 is .rela.dyn
        0x0000000000000760 - 0x0000000000000850 is .rela.plt
        0x0000000000001000 - 0x000000000000101b is .init
        0x0000000000001020 - 0x00000000000010d0 is .plt
        0x00000000000010d0 - 0x00000000000010e0 is .plt.got
        0x00000000000010e0 - 0x0000000000001180 is .plt.sec
        0x0000000000001180 - 0x00000000000029c5 is .text
        0x00000000000029c8 - 0x00000000000029d5 is .fini
        0x0000000000003000 - 0x0000000000003279 is .rodata
        0x000000000000327c - 0x0000000000003358 is .eh_frame_hdr
        0x0000000000003358 - 0x00000000000036c8 is .eh_frame
        0x0000000000004d70 - 0x0000000000004d78 is .init_array
        0x0000000000004d78 - 0x0000000000004d80 is .fini_array
        0x0000000000004d80 - 0x0000000000004f70 is .dynamic
        0x0000000000004f70 - 0x0000000000005000 is .got
        0x0000000000005000 - 0x0000000000005010 is .data
        0x0000000000005010 - 0x0000000000005020 is .bss
(gdb) break memcmp
Breakpoint 1 at 0x1130
(gdb) run
Starting program: /challenge/trust-the-yancode-hard 
[+] Welcome to /challenge/trust-the-yancode-hard!
[+] This challenge is an custom emulator. It emulates a completely custom
[+] architecture that we call "Yan85"! You'll have to understand the
[+] emulator to understand the architecture, and you'll have to understand
[+] the architecture to understand the code being emulated, and you will
[+] have to understand that code to get the flag. Good luck!
[+]
[+] This is an introductory Yan85 level, where we trigger Yan85 architecture
[+] operations directly. The parts of Yan85 that are used here is the emulated
[+] registers, memory, and system calls.
test

Breakpoint 1.1, __memcmp_sse4_1 ()
    at ../sysdeps/x86_64/multiarch/memcmp-sse4.S:43
warning: 43     ../sysdeps/x86_64/multiarch/memcmp-sse4.S: No such file or directory
(gdb) x/16bx $rdi
0x7fff1dd57b23: 0xe9    0x90    0x29    0x2f    0xbb    0x4f    0x76    0xa0
0x7fff1dd57b2b: 0x00    0x00    0x00    0x00    0x00    0x00    0x00    0x00
(gdb) x/16bx $rsi
0x7fff1dd57b03: 0x74    0x65    0x73    0x74    0x0a    0x00    0x00    0x00
0x7fff1dd57b0b: 0x00    0x00    0x00    0x00    0x00    0x00    0x00    0x00
(gdb) print $rdx
$1 = 8
(gdb) exit
A debugging session is active.

        Inferior 1 [process 1639] will be killed.

Quit anyway? (y or n) y
hacker@reverse-engineering~trust-the-yancode-hard:/challenge$ python3 -c 'import sys; sys.stdout.buffer.write(bytes([0xe9, 0x90, 0x29, 0x2f, 0xbb, 0x4f, 0x76, 0xa0]))' | ./trust-the-yancode-hard
[+] Welcome to ./trust-the-yancode-hard!
[+] This challenge is an custom emulator. It emulates a completely custom
[+] architecture that we call "Yan85"! You'll have to understand the
[+] emulator to understand the architecture, and you'll have to understand
[+] the architecture to understand the code being emulated, and you will
[+] have to understand that code to get the flag. Good luck!
[+]
[+] This is an introductory Yan85 level, where we trigger Yan85 architecture
[+] operations directly. The parts of Yan85 that are used here is the emulated
[+] registers, memory, and system calls.
CORRECT! Your flag:
pwn.college{8bpWOdHH-GUmflYwnxn9JoZbai5.0FN3IDLyMjN0czW}
```
