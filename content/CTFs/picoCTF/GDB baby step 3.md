---
title: GDB baby step 3
ctf: "[[picoCTF]]"
category: "[[Reverse Engineering]]"
difficulty: "[[Medium]]"
points: 0
status: Solved
flag_format: picoCTF{...}
tags:
  - ctf
  - reverse
  - engineering
  - medium
  - x86_64
link: https://play.picoctf.org/practice/challenge/397
created: 2025-05-18T21:28
updated: 2025-05-18T22:06
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/397)

Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`.
The flag is the four bytes as they are stored in memory. 
If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`. 
Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).

# Approach and Steps

I started with `gdb debugger0_c` to load the file into the debugger. 

Disassembled it using `disass main` and go the following.
```Js
Dump of assembler code for function main:
   0x0000000000401106 <+0>:	endbr64
   0x000000000040110a <+4>:	push   %rbp
   0x000000000040110b <+5>:	mov    %rsp,%rbp
   0x000000000040110e <+8>:	mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:	mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:	movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:	mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:	pop    %rbp
   0x0000000000401120 <+26>:	ret
End of assembler dump.
```

Added breakpoint at `0x000000000040111c` by running `b *0x000000000040111c` and then `run` the program

Examined the memory using ` x/4xb $rpb-0x4` to get the flag.
```js
0x7fffffffd9cc:	0x6b	0xc9	0x62	0x22
```

The flag is just the reverse bytes of `$0x2262c96b` which we found in disassembly because the program's [[Endianness]] is little endian.
# Flag

> [!success] Flag
> `picoCTF{0x6bc96222}`

# Tools Used

[[gdb]]
