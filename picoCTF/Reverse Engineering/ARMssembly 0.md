# ARMssembly 0

## Challenge Description

What integer does this program print with arguments 4112417903 and 1169092511? File: chall.S Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

## Hints

Simple compare

## Solution

```bash
	.arch armv8-a
	.file	"chall.c"
	.text
	.align	2
	.global	func1
	.type	func1, %function
func1:
	sub	sp, sp, #16
	str	w0, [sp, 12]
	str	w1, [sp, 8]
	ldr	w1, [sp, 12]
	ldr	w0, [sp, 8]
	cmp	w1, w0
	bls	.L2
	ldr	w0, [sp, 12]
	b	.L3
.L2:
	ldr	w0, [sp, 8]
.L3:
	add	sp, sp, 16
	ret
	.size	func1, .-func1
	.section	.rodata
	.align	3
.LC0:
	.string	"Result: %ld\n"
	.text
	.align	2
	.global	main
	.type	main, %function
main:
	stp	x29, x30, [sp, -48]!
	add	x29, sp, 0
	str	x19, [sp, 16]
	str	w0, [x29, 44]
	str	x1, [x29, 32]
	ldr	x0, [x29, 32]
	add	x0, x0, 8
	ldr	x0, [x0]
	bl	atoi
	mov	w19, w0
	ldr	x0, [x29, 32]
	add	x0, x0, 16
	ldr	x0, [x0]
	bl	atoi
	mov	w1, w0
	mov	w0, w19
	bl	func1
	mov	w1, w0
	adrp	x0, .LC0
	add	x0, x0, :lo12:.LC0
	bl	printf
	mov	w0, 0
	ldr	x19, [sp, 16]
	ldp	x29, x30, [sp], 48
	ret
	.size	main, .-main
	.ident	"GCC: (Ubuntu/Linaro 7.5.0-3ubuntu1~18.04) 7.5.0"
	.section	.note.GNU-stack,"",@progbit
```

Since my knowledge in assembly language is not that great, I used an [online assembly to c converter](https://www.codeconvert.ai/assembly-to-c-converter) to better understand what's going on in the code. Following is the equivalent C code of the program

```bash
#include <stdio.h>
#include <stdlib.h>

int func1(int a, int b) {
    if (b <= a) {
        return a;
    } else {
        return b;
    }
}

int main(int argc, char *argv[]) {
    int a, b;
    if (argc > 1) {
        a = atoi(argv[1]);
    }
    if (argc > 2) {
        b = atoi(argv[2]);
    }
    int result = func1(a, b);
    printf("Result: %d\n", result);
    return 0;
}
```
From the code it's clear that the program takes two command-line arguments, converts them to integers, compares them, and prints the larger number. So 4112417903 will be printed since it's the larger integer. Since the flag requires the integer to be in hex, I converted it to hex format with lowercase, no 0x, and 32 bits

![image](https://github.com/user-attachments/assets/f3f5708b-535a-402a-9400-027ed2099139)

Thus the flag for this challenge is `picoCTF{f51e846f}`
