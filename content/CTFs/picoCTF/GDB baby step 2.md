---
title: GDB baby step 2
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
link: https://play.picoctf.org/practice/challenge/396
created: 2025-05-18T18:19
updated: 2025-05-18T22:06
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/396)

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).
# Approach and Steps

Run `gdb debugger0_b` to start debugging the binary.

```js
(gdb) disass main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:	endbr64
   0x000000000040110a <+4>:	push   %rbp
   0x000000000040110b <+5>:	mov    %rsp,%rbp
   0x000000000040110e <+8>:	mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:	mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:	movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:	movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:	movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:	jmp    0x401136 <main+48>
   0x000000000040112c <+38>:	mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:	add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:	addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:	mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:	cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:	jl     0x40112c <main+38>
   0x000000000040113e <+56>:	mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:	pop    %rbp
   0x0000000000401142 <+60>:	ret
End of assembler dump.
```

Set breakpoint after eax is calculated
```Js
(gdb) b *0x0000000000401141
Breakpoint 1 at 0x401141
```

Print eax
```JS
gdb) p $eax
$1 = 307019
```
# Flag

> [!success] Flag
> `picoCTF{307019}`

# Tools Used

[[gdb]]