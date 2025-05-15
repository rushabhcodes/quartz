## TCP/IP Vulnerabilities Layerwise

The TCP/IP model has multiple layers, and each has specific vulnerabilities that attackers can exploit.

---

### 1. **Application Layer Vulnerabilities**

- **Description:** This is where applications and services operate (HTTP, FTP, DNS, SMTP, etc.).
    
- **Common Vulnerabilities:**
    
    - **Buffer Overflow:** Malicious input overruns memory causing crashes or code execution.
        
    - **Injection Attacks:** [[SQL Injection]], Command Injection targeting application logic.
        
    - **Session Hijacking:** Stealing or predicting session tokens.
        
    - **DNS Spoofing/Cache Poisoning:** Redirecting users to malicious sites by corrupting DNS data.
        
    - **Email Spoofing:** Faking sender’s address in SMTP to deliver phishing or spam.
        

---

### 2. **Transport Layer Vulnerabilities**

- **Description:** Manages end-to-end communication (TCP, UDP).
    
- **Common Vulnerabilities:**
    
    - **TCP SYN Flood Attack:** Exploits the TCP handshake by sending many SYN requests and never completing the handshake, exhausting server resources.
        
    - **Session Hijacking:** Intercepting or predicting sequence numbers to take over active TCP sessions.
        
    - **UDP Flooding:** Overwhelming a target with UDP packets, causing resource exhaustion.
        

---

### 3. **Internet Layer Vulnerabilities**

- **Description:** Responsible for routing packets across networks (IP, ICMP).
    
- **Common Vulnerabilities:**
    
    - **IP Spoofing:** Sending IP packets with a forged source IP address to hide attacker identity or bypass filters.
        
    - **Smurf Attack:** Using ICMP echo requests broadcasted to a network with the victim's IP spoofed as the source, causing a flood of replies to the victim.
        
    - **Fragmentation Attacks:** Sending fragmented IP packets to evade detection or cause system crashes.
        

---

### 4. **Network Interface Layer Vulnerabilities**

- **Description:** Handles physical network hardware and data link protocols (Ethernet, ARP).
    
- **Common Vulnerabilities:**
    
    - **MAC Spoofing:** Changing the MAC address to impersonate another device.
        
    - **ARP Spoofing/Poisoning:** Sending fake ARP messages to associate attacker’s MAC with IP of a legitimate host, enabling man-in-the-middle attacks.
        
    - **Switch Spoofing & VLAN Hopping:** Manipulating VLAN tags to gain unauthorized access to network segments.
        

---

## Summary Table

|TCP/IP Layer|Common Vulnerabilities|Attack Examples|
|---|---|---|
|Application Layer|Injection, Buffer Overflow, DNS Spoofing|SQL Injection, Email Spoofing|
|Transport Layer|SYN Flood, Session Hijacking|TCP SYN Flood|
|Internet Layer|IP Spoofing, Smurf, Fragmentation|IP Spoofing, Smurf Attack|
|Network Interface Layer|ARP Spoofing, MAC Spoofing, VLAN Hopping|ARP Poisoning, MAC Spoofing|
