---
title: GDB baby step 4
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
link: https://play.picoctf.org/practice/challenge/398
created: 2025-05-18T22:08
updated: 2025-05-18T22:17
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/398)

`main` calls a function that multiplies `eax` by a constant. The flag for this challenge is that constant in decimal base. If the constant you find is 0x1000, the flag will be `picoCTF{4096}`. Debug [this](https://artifacts.picoctf.net/c/532/debugger0_d).

# Approach and Steps

This was another simple challenge that can be solved by looking at the assembly code.

`disass main`
```js
Dump of assembler code for function main:
   0x000000000040111c <+0>:	endbr64
   0x0000000000401120 <+4>:	push   %rbp
   0x0000000000401121 <+5>:	mov    %rsp,%rbp
   0x0000000000401124 <+8>:	sub    $0x20,%rsp
   0x0000000000401128 <+12>:	mov    %edi,-0x14(%rbp)
   0x000000000040112b <+15>:	mov    %rsi,-0x20(%rbp)
   0x000000000040112f <+19>:	movl   $0x28e,-0x4(%rbp)
   0x0000000000401136 <+26>:	movl   $0x0,-0x8(%rbp)
   0x000000000040113d <+33>:	mov    -0x4(%rbp),%eax
   0x0000000000401140 <+36>:	mov    %eax,%edi
   0x0000000000401142 <+38>:	call   0x401106 <func1>
   0x0000000000401147 <+43>:	mov    %eax,-0x8(%rbp)
   0x000000000040114a <+46>:	mov    -0x4(%rbp),%eax
   0x000000000040114d <+49>:	leave
   0x000000000040114e <+50>:	ret
End of assembler dump.
```

Now look into func1

`disass func1`
```js
Dump of assembler code for function func1:
   0x0000000000401106 <+0>:	endbr64
   0x000000000040110a <+4>:	push   %rbp
   0x000000000040110b <+5>:	mov    %rsp,%rbp
   0x000000000040110e <+8>:	mov    %edi,-0x4(%rbp)
   0x0000000000401111 <+11>:	mov    -0x4(%rbp),%eax
   0x0000000000401114 <+14>:	imul   $0x3269,%eax,%eax
   0x000000000040111a <+20>:	pop    %rbp
   0x000000000040111b <+21>:	ret
End of assembler dump.
```

Here we get the constant `$0x3269`

We convert it int decimal using python.
```python
python
Python 3.13.3 (main, Apr  9 2025, 07:44:25) [GCC 14.2.1 20250207] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x3269
12905
>>> 
```
# Flag

> [!success] Flag
> `picoCTF{12905}`

# Tools Used

[[gdb]]