## Challenge Info
- **Name:** PIE TIME
- **Category:** [[Binary Exploitation]] [[picoCTF 2025]]
- **Level:** [[Easy]]
- **Link:** https://play.picoctf.org/practice/challenge/490
- **Description:**
	- Can you try to get the flag? Beware we have PIE!
	  Connect to the program with netcat:
	- ```
	  $ nc rescued-float.picoctf.net 49787 
	  ```
	- The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_rescued_float/2757d7751ddf1be98450094c20e981031e6c654474ddeb8f646f6d98e3832c15/vuln.c). The binary can be downloaded [here](https://challenge-files.picoctf.net/c_rescued_float/2757d7751ddf1be98450094c20e981031e6c654474ddeb8f646f6d98e3832c15/vuln).
- ## Problem Understanding
  > "First i didn't get what PIE TIME meant then after a little search i found out that PIE means [Position-independent code](https://en.wikipedia.org/wiki/Position-independent_code).
- ## Approach and Steps
- [Step 1]
  logseq.order-list-type:: number
	- Tried to understand `vuln.c`
	- The program tries to run a function which is located at the address give by the user in the cli.
- [Step 2]
  logseq.order-list-type:: number
	- Tried giving random address to test, got segfault.
- [Step 3]
  logseq.order-list-type:: number
	- Got to know about [[gdb]] a [[cli-tool]]
	- Used gdb on vuln
- [Step 4]
  logseq.order-list-type:: number
	- In (gdb) run: `disass main` which game me the assembly code of main with it's location in memory. Start location was `0x000000000000133d`
	- In (gdb) run: `disass win` which game me the assembly code of win with it's location in memory. Start location was `0x00000000000012a7`
	- Therefore `0x000000000000133d` -  `0x00000000000012a7` = `0x96` , the run run function is 96 addresses before main.
- [Step 5]
  logseq.order-list-type:: number
	- Subtracted `0x96` form the address of main which is provided in the cli and the program gives the flag.
	-
- ## Solution
- The flag was: `picoCTF{b4s1c_p051t10n_1nd3p3nd3nc3_93dd5fcb}`
  
  ---
- ## Tools Used
- [[gdb]]
- [[nc]]
- ---