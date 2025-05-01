---
title: Scan Surprise
ctf: "[[picoCTF]]"
category: "[[Forenscis]]"
difficulty: "[[Easy]]"
points: 0
status: Solved
flag_format: picoCTF{...}
date: 2025-04-30
tags:
  - ctf
  - picoctf
  - forenscis
  - easy
  - picocCTF2024
link: https://play.picoctf.org/practice/challenge/444
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/444)
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

You can download the challenge files here: [challenge.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

The same files are accessible via SSH here: `ssh -p 51989 ctf-player@atlas.picoctf.net`  
Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
# Approach and Steps 
- `ssh -p 51989 ctf-player@atlas.picoctf.net` into the server which showed a qr code
- Scanning the qr code with my phone gave the flag
# Flag

> [!success] Flag
>`picoCTF{p33k_@_b00_a81f0a35}` 

# Tools Used
[[ssh]]