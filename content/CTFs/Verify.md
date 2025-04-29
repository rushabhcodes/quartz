## Challenge Info
	- **Name:** Verify
	- **Category:** [[Forenscis]] [[picoCTF 2024]]
	- **Level:** [[Easy]]
	- **Link:** https://play.picoctf.org/practice/challenge/450
	- **Description:**
		- People keep trying to trick my players with imitation flags. I want to make sure  they get the real thing! I'm going to provide the SHA-256 hash and a  decrypt script to help you know that my flags are legitimate.
		  `ssh -p 52595 ctf-player@rhea.picoctf.net`
		  Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
		- Checksum: 3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4
		- To decrypt the file once you've verified the hash, run `./decrypt.sh files/<file>`.
- ## Problem Understanding
	- Now clue what i need to to , so i `ssh` into the given server.
	- There are many files in the `/files` directory with random name and a decrypt script in the root directory.
	- The goal was to decrypt the correct file.
- ## Approach and Steps
- [Step 1]
  logseq.order-list-type:: number
	- Try to decrypt a random file with the given script which returned gibberish.
- [Step 2]
  logseq.order-list-type:: number
	- View the hints
		- Hint 1
		  logseq.order-list-type:: number
			- Checksums let you tell if a file is complete and 
			  from the original distributor. If the hash doesn't match, it's a 
			  different file.
		- Hint 2
		  logseq.order-list-type:: number
			- You can create a SHA checksum of a file with `sha256sum <file>` or all files in a directory with `sha256sum <directory>/*`.
		- Hint 3
		  logseq.order-list-type:: number
			- Remember you can pipe the output of one command to another with `|`. Try practicing with the 'First Grep' challenge if you're stuck!
			-
- [Step 3]
  logseq.order-list-type:: number
	- `sha256sum files/*` gave shecksum of all files
	- `checksum files/* | grep 3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4` gave the file in which the flag exist.
- ## Solution
- The flag was: `picoCTF{trust_but_verify_e018b574}`
  
  ---
- ## Reflections (Optional)
	- Learned about a new too [[sha256sum]]
- ## Tools Used
	- [[ssh]]
	- [[grep]]
	- [[|]]
	- [[sha256sum]]