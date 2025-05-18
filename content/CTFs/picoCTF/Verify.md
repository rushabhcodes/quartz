---
title: Verify
ctf: "[[picoCTF]]"
category: "[[Forensics]]"
difficulty: "[[Easy]]"
points: 0
status: Solved
flag_format: picoCTF{...}
date: 2025-04-30
tags:
  - ctf
  - picoctf
  - easy
  - forensics
  - picocCTF2024
link: https://play.picoctf.org/practice/challenge/450
created: 2025-05-16T10:37
updated: 2025-05-18T15:12
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/450)
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

`ssh -p 52595 ctf-player@rhea.picoctf.net`  

Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!  

Checksum: `3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4`
To decrypt the file once you've verified the hash, run `./decrypt.sh files/`.
Additional details will be available after launching your challenge instance.
# Approach and Steps 
Try to decrypt a random file with the given script which returned gibberish.

- View the hints
	-  Hint 1
		- Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.  
	- Hint 2
		- You can create a SHA checksum of a file with `sha256sum` or all files in a directory with `sha256sum /*`.
	- Hint 3
		- Remember you can pipe the output of one command to another with `|`. Try practicing with the 'First Grep' challenge if you're stuck!

`sha256sum files/*` gave shecksum of all files

 `checksum files/* | grep 3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4` gave the file in which the flag exist.
# Flag

> [!success] Flag
> `picoCTF{trust_but_verify_e018b574}`

# Tools Used
[[ssh]]
[[grep]]
[[Pipe Operator]]
[[sha256sum]]