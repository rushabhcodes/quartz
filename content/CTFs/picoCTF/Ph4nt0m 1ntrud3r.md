---
title: Ph4nt0m 1ntrud3r
ctf: "[[picoCTF]]"
category: "[[Forensics]]"
difficulty: "[[Easy]]"
points: 0
status: Solved
flag_format: picoCTF{...}
date: 2025-05-01
tags:
  - ctf
  - picoctf
  - forensics
  - easy
  - picocCTF2025
link: https://play.picoctf.org/practice/challenge/459
created: 2025-05-08T18:50
updated: 2025-05-08T18:50
---
# [Challenge Description](https://play.picoctf.org/practice/challenge/459)
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided [[PCAP]] file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! 

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.
# Approach and Steps
Open Wireshark with `myNetworkTraffic.pcap`

All the requests were `TCP Retransimtteed`

After looking at the hints i filtered them by time and the last few transmissions had the flag.	
```
cGljb0NURg=
ezF0X3c0cw==
bnRfdGg0dA==
XzM0c3lfdA==
YmhfNHJfOQ==
NTlmNTBkMw==
fQ==
```
But i manually typed each base64 data in the converte, i an sure there is a better way to do it.
```
picoCTF
{1t_w4s
nt_th4t
_34sy_t
bh_4r_9
59f50d3
}
```
# Flag

> [!success] Flag
>`picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}` 

# Tools Used
[[Wireshark]]