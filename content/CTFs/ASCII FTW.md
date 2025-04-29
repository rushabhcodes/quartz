## Challenge Info
	- **Name**: ASCII FTW
	- **Category**: [[Reverse Engineering]]
	- **Level:** [[Medium]]
	- **Link:** https://play.picoctf.org/practice/challenge/389
	- **Description:**
	  
	  This program constructs the flag using hex ASCII values. We are tasked with disassembling the program and identifying the flag text hidden inside.
	  A binary file named `asciiftw` is provided.
	  ---
- ## Problem Understanding
  
  The disassembly of the binary shows that it moves a sequence of **hexadecimal byte values** into memory. Each hex value corresponds to an ASCII character. By reading these hex values and converting them to ASCII, we can reconstruct the flag.
  
  ---
- ## Approach and Steps
  
  **Step 1**
	- What I did first:
	  
	  Downloaded the binary and loaded it into GDB.
	- Tools, commands, or techniques used:
	  
	  ```
	  gdb asciiftw
	  ```
- **Step 2**
	- What I did next:
	  
	  Disassembled the `main` function to inspect how the flag was built.
	- Tools, commands, or techniques used:
	  
	  ```
	  (gdb) disassemble main
	  ```
- **Step 3**
	- How I solved the challenge:
		- Observed a series of instructions like `movb $0x70, -0x30(%rbp)` which store bytes into memory.
		- Used **regex** to extract all the hexadecimal byte values from the disassembly:
		  
		  ```
		  \$0x([0-9a-fA-F]+)
		  ```
		  
		  (This matches all the hex numbers like `$0x70`, `$0x69`, etc.)
		- Retrieved the hex sequence:
		  
		  ```
		  70 69 63 6f 43 54 46 7b 41 53 43 49 49 5f 49 53 5f 45 41 53 59 5f 38 39 36 30 46 30 41 46 7d
		  ```
		- Converted the hex values to ASCII, yielding:
		  
		  ```
		  picoCTF{ASCII_IS_EASY_8960F0AF}
		  ```
		  
		  ---
- ## Solution
  
  The flag is:
  
  ```
  picoCTF{ASCII_IS_EASY_8960F0AF}
  ```
  
  ---
- ## Reflections (Optional)
	- This was a straightforward binary where regex automation greatly sped up the manual process.
	  ---
- ## Tools Used
	- [[GDB]]
	- [[Regex]] (`\$0x([0-9a-fA-F]+)`)
	  ---