---
created: 2025-05-15T09:00
updated: 2025-05-15T09:01
---
**Definition:**  
ARP spoofing is an attack where the attacker sends **fake ARP messages** to associate their MAC address with the IP of another device (like a gateway).

**Goal:**  
Intercept, modify, or block traffic (i.e., **Man-in-the-Middle attack**).

**How it works:**

- ARP is a protocol that maps IP addresses to MAC addresses.
    
- The attacker sends forged ARP replies to the victim and the gateway.
    
- Both end up sending data to the attacker.
    

**Impact:**

- Intercept sensitive data.
    
- Denial of service.
    
- Session hijacking.
    

**Tools:** Cain & Abel, Ettercap, arpspoof

**Prevention:**

- Use **static ARP entries**.
    
- Implement **ARP inspection** (e.g., Dynamic ARP Inspection on switches).
    
- Use **encrypted protocols** (SSH, HTTPS).