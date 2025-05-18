---
title: GDB baby step 1
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
link: https://play.picoctf.org/practice/challenge/395
created: 2025-05-18T17:57
updated: 2025-05-18T22:06
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/395)

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

# Approach and Steps

Run `gdb debugger0_a` to start debugging the binary.


Found this line by running `dissass main`
`0x0000000000001138 <+15>:	mov    $0x86342,%eax`

Converted `0x86342` to decimal and got `549698`.

# Flag

> [!success] Flag
> `picoCTF{549698}`

# Tools Used

[[gdb]]