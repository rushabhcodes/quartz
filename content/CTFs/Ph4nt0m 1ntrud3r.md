- ## Challenge Info
	- **Name:** Ph4nt0m 1ntrud3r
	- **Category:** [[Forenscis]] [[picoCTF 2025]]
	- **Level:** [[Easy]]
	- **Link:** https://play.picoctf.org/practice/challenge/459
	- **Description:**  
	  A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 
	   Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.
	   To solve this challenge, you'll need to analyze  the provided PCAP file and track down the attack method. The attacker  has cleverly concealed his moves in well timely manner. Dive into the 
	   network traffic, apply the right filters and show off your forensic  prowess and unmask the digital intruder!
	   Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.
	   ---
- ## Problem Understanding
  > A [[PCAP]] file is a packet capture created by [[Wireshark]] , this made it clear that i needed Wireshark.
  
  ---
- ## Approach and Steps
	- [Step 1]
	  logseq.order-list-type:: number
		- Open Wireshark with `myNetworkTraffic.pcap`
	- [Step 2]
	  logseq.order-list-type:: number
		- All the requests were `TCP Retransimtteed`
	- [Step 3]
	  logseq.order-list-type:: number
		- After looking at the hints i filtered them by time and the last few transmissions had the flag.
		- ```
		  cGljb0NURg=
		  ezF0X3c0cw==
		  bnRfdGg0dA==
		  XzM0c3lfdA==
		  YmhfNHJfOQ==
		  NTlmNTBkMw==
		  fQ==
		  ```
		- ```
		  picoCTF
		  {1t_w4s
		  nt_th4t
		  _34sy_t
		  bh_4r_9
		  59f50d3
		  }
		  ```
		- But i manually typed each base64 data in the converte, i an sure there is a better way to do it.
- ## Solution
	- The flag was: `picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}`
	  
	  ---
- ## Reflections (Optional)
	- [Any insights or things you learned during the challenge]
	- [What would you do differently next time or what could improve efficiency]
	  
	  ---
- ## Tools Used
	- [[Wireshark]]
	- [Base64Converter](https://www.base64decode.org/)
-