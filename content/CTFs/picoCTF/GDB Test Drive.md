---
title: GDB Test Drive
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
  - picocCTF2022
  - binary
link: https://play.picoctf.org/practice/challenge/273
created: 2025-05-19T08:30
updated: 2025-05-19T08:40
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/273)

Can you get the flag? Download this [binary](https://artifacts.picoctf.net/c/86/gdbme). Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
# Approach and Steps 

Just follow the given steps
# Flag

> [!success] Flag
> `picoCTF{d3bugg3r_dr1v3_72bd8355}`

# Tools Used

[[gdb]]