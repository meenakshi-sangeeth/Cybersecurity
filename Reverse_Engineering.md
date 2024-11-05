# GDB baby step 1

## Challenge Decsription

Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Disassemble *this*

## Hints
	- gdb is a very good debugger to use for this problem and many others!
	- `main` is actually a recognized symbol that can be used with gdb commands

## Thought Process

The challenge is to perform reverse engineering on the attached file using GDB and find the value contained in the eax register at the end of the main function. So first of all I'll have to intsall `gdb` since it isn't installed on my system. Once it is installed, I'll have to open the binary file (which was attached in the challenge description) in `gdb` by passing the file as argument. Now my aim is to disassemble the main function since the value I need is in the eax register, which is present in the main function. The disassembling of the function is done in order to convert machine code (the binary instructions present in the file) back into assembly language so that it'll be easier for me to understand and analyse. After the disassembling is done, I should be able to find the eax register along with the required value. The value should then be converted into decimal number base as mentioned in the challenge


## Solution

To install `gdb`, I executed the following command
```bash
apt install gdb```
After the installation, I opened the file (debugger0_a) using 
```bash
gdb debugger0_a```
Now to disassemble the main function, I used the command
```bash
disassemble main```
After execution the following output was generated
```bash
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
```
Thus I found the required value `0x86342` mentioned beside `eax` register towards the end of the `main` function, as mentioned in the challenge description. Then I converted the value into decimal number system using an online hex to decimal converter which gave me the value `549698`.

Therefore, the flag for this challenge is picoCTF{549698} 

## Concepts Learned

	- In assembly language, AT&T and Intel syntax are two different formats for writing assembly code instructions. The following is a brief overview of both the formats
		- Order of Operands
		* Intel Syntax: `destination, source``
			Example: `mov eax, ebx` (move the contents of `ebx` into `eax`)
		* AT&T Syntax: `source, destination`
			Example: `movl %ebx, %eax` (same instruction, but the source comes first)
		So, in Intel, you write where the data is going first, while in AT&T, you write where it’s coming from first.
		
		- Registers and Immediate Values
		* Intel Syntax: Registers are written without any special symbols, and immediate (constant) values have `0x` for hex.
			Example: `eax`, `ebx`
		* AT&T Syntax: Registers have a `%` prefix, and hex values have `$` as a prefix.
			Example: `%eax`, `$0x10`
			
		- Suffix for Operand Size
		* Intel Syntax: The size of the operand is often inferred from the registers
			Example: `mov eax, 10` (Intel assumes this is a 32-bit operation)
		* AT&T Syntax: Uses suffixes to indicate operand size - b for byte (8-bit), w for word (16-bit), l for long (32-bit), and q for quadword (64-bit).
			Example: `movl $10, %eax` (the l suffix indicates a 32-bit move)
			
		- Memory Access
		* Intel Syntax: Uses `[]` for memory references
			Example: `mov eax, [ebx+4]` (moves the value at `ebx+4` into `eax`)
		* AT&T Syntax: Uses `()` for memory references.
			Example: `movl 4(%ebx), %eax`
	- GDB's syntax is set to AT&T by default
	- You can open a file using `gdb` by passing the file name as the argument
	- Disassembling a function can be done using `disassemble <function_name>`
	- You can quit `gdb` using `q`

## Incorrect Tangents

While I was trying to open the file, I didn't make sure that the file was present in the current working directory which resulted in error

