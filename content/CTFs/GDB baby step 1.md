## Challenge Info
	- **Name**: GDB baby step 1
	- **Category**: [[Reverse Engineering]]
	- **Level:** [[Medium]]
	- **Author**: LT 'syreal' Jones
	- **Points**: 100
	- **Link**: [Challenge site link or artifact provided]
	  
	  ---
- ## Description
	- Can you figure out what is in the `eax` register at the end of the `main` function?
	  
	  Submit your answer in picoCTF flag format: `picoCTF{n}`, where `n` is the contents of the `eax` register **in decimal**.
	  
	  Given file: `debugger0_a`
	  
	  ---
- ## Problem Understanding
  
  The challenge wants us to inspect the assembly code of the binary and determine what value is loaded into the `eax` register before the function `main` returns.
  
  ---
- ## Approach and Steps
	- **Step 1**
		- What I did first:
		  
		  Downloaded the provided binary.
		- Tools, commands, or techniques used:
		  
		  ```
		  curl -O https://artifacts.picoctf.net/c/512/debugger0_a
		  ```
	- **Step 2**
		- What I did next:
		  
		  Opened the binary in GDB and disassembled the `main` function.
		- Tools, commands, or techniques used:
		  
		  ```
		  gdb debugger0_a
		  (gdb) disass main
		  ```
	- **Step 3**
		- How I solved the challenge:
		  
		  From the disassembly output, it is clear that the instruction:
		  
		  ```
		  mov $0x86342, %eax
		  ```
		  
		  loads the value `0x86342` into `eax`.
		  
		  To convert this to decimal:
		  
		  ```
		  >>> int("0x86342", 16)
		  548162
		  ```
		  
		  Thus, the value in decimal is **548162**.
		  
		  ---
- ## Solution
  
  The flag is:
  
  ```
  picoCTF{548162}
  ```
  
  ---
- ## Reflections (Optional)
	- Learned a basic check of registers via disassembly without even running the program.
	  ---
- ## Tools Used
	- [[gdb]]
	- [[Python]] (for hex-to-decimal conversion)
	  
	  ---