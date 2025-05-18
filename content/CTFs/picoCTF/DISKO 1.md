---
title: DISKO 1
ctf: "[[picoCTF]]"
category: "[[Forensics]]"
difficulty: "[[Easy]]"
points: 0
status: Solved
flag_format: picoCTF{...}
tags:
  - ctf
  - forensics
  - easy
link: https://play.picoctf.org/practice/challenge/505
created: 2025-05-18T15:02
updated: 2025-05-18T17:55
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/505)

Can you find the flag in this disk image?
Download the disk image [here](https://artifacts.picoctf.net/c/536/disko-1.dd.gz).

# Approach and Steps

Downloaded the file and extracted it using `gunzip`.

Running strings with grep reveals the flag.

`strings disko-1.dd | grep picoCTF`

# Flag

> [!success] Flag
> `picoCTF{1t5_ju5t_4_5tr1n9_c63b02ef}`

# Tools Used
[[strings]]
[[grep]]
[[gunzip]]