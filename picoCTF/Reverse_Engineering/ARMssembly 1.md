# ARMssembly 1

## Challenge Decsription

For what argument does this program print `win` with variables 79, 7 and 3? 
File: chall_1.S 
Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

## Thought Process

I opened the attached file 
```bash
.arch armv8-a
	.file	"chall_1.c"
	.text
	.align	2
	.global	func
	.type	func, %function
func:
	sub	sp, sp, #32
	str	w0, [sp, 12]
	mov	w0, 79
	str	w0, [sp, 16]
	mov	w0, 7
	str	w0, [sp, 20]
	mov	w0, 3
	str	w0, [sp, 24]
	ldr	w0, [sp, 20]
	ldr	w1, [sp, 16]
	lsl	w0, w1, w0
	str	w0, [sp, 28]
	ldr	w1, [sp, 28]
	ldr	w0, [sp, 24]
	sdiv	w0, w1, w0
	str	w0, [sp, 28]
	ldr	w1, [sp, 28]
	ldr	w0, [sp, 12]
	sub	w0, w1, w0
	str	w0, [sp, 28]
	ldr	w0, [sp, 28]
	add	sp, sp, 32
	ret
	.size	func, .-func
	.section	.rodata
	.align	3
.LC0:
	.string	"You win!"
	.align	3
.LC1:
	.string	"You Lose :("
	.text
	.align	2
	.global	main
	.type	main, %function
main:
	stp	x29, x30, [sp, -48]!
	add	x29, sp, 0
	str	w0, [x29, 28]
	str	x1, [x29, 16]
	ldr	x0, [x29, 16]
	add	x0, x0, 8
	ldr	x0, [x0]
	bl	atoi
	str	w0, [x29, 44]
	ldr	w0, [x29, 44]
	bl	func
	cmp	w0, 0
	bne	.L4
	adrp	x0, .LC0
	add	x0, x0, :lo12:.LC0
	bl	puts
	b	.L6
.L4:
	adrp	x0, .LC1
	add	x0, x0, :lo12:.LC1
	bl	puts
.L6:
	nop
	ldp	x29, x30, [sp], 48
	ret
	.size	main, .-main
	.ident	"GCC: (Ubuntu/Linaro 7.5.0-3ubuntu1~18.04) 7.5.0"
	.section	.note.GNU-stack,"",@progbits
```

Now let's analyse the program to get a faint idea of what's going on

- Breakdown of `func`:
  1. The function sets up the stack and initializes local variables:
     - Variable at `[sp, 16]` = `79`
     - Variable at `[sp, 20]` = `7`
     - Variable at `[sp, 24]` = `3`
     - The function argument is stored at `[sp, 12]`
  2. Calculation Logic:
     - `ldr w0, [sp, 20]` → Load 7 into w0
     - `ldr w1, [sp, 16]` → Load 79 into w1
     - `lsl w0, w1, w0` → Perform w1 << w0 (bitwise left shift): 79 << 7 = 10112
     - `str w0, [sp, 28]` → Store 10112 at [sp, 28]
     - `ldr w1, [sp, 28]` → Load 10112 into w1
     - `ldr w0, [sp, 24]` → Load 3 into w0
     - `sdiv w0, w1, w0` → Perform integer division 10112 / 3: Result = 3370 (integer division)
     - `str w0, [sp, 28]` → Store 3370 at [sp, 28]
     - `ldr w1, [sp, 28]` → Load 3370 into w1
     - `ldr w0, [sp, 12]` → Load the function argument (stored initially) into w0
     - `sub w0, w1, w0` → Perform subtraction 3370 - w0
     - `str w0, [sp, 28]` → Store the result of subtraction at [sp, 28]
     - `ldr w0, [sp, 28]` → Load the final result into w0
     - The function returns the result stored in w0

- Breaksdown of `main`:
  The main function passes the argument from the command line (converted to an integer using atoi) to func.
  After func returns:
  - If w0 == 0, the program prints "You win!"
  - If w0 != 0, the program prints "You Lose :("

## Solution

The challenge requires the program to print "You win!". For that `w0`, which is the result of subtraction at `[sp, 28]`, should be 0. This happens when 3370 − argument = 0 which implies argument = 3370. After converting 3370 into hex, lowercase, no 0x, and 32 bits we get 00000d2a. Thus the flag for this challenge is `picoCTF{00000d2a}`

