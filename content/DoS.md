---
created: 2025-05-15T08:50
updated: 2025-05-15T08:56
---
## What is a DoS Attack?

**DoS (Denial of Service) Attack** is a cyberattack aimed at making a network, service, or system unavailable to its intended users by overwhelming it with excessive traffic or exploiting vulnerabilities. The goal is to **disrupt normal functioning** so legitimate users cannot access resources like websites, servers, or applications.

---

## Different Ways to Mount DoS Attacks

### 1. **Flood Attacks**

- **Description:** Overwhelm the target with a massive volume of traffic or requests.
    
- **Types:**
    
    - **[[ICMP Flood]] (Ping Flood):** Sends large numbers of ICMP Echo Request packets (pings) to consume bandwidth and resources.
        
    - **UDP Flood:** Sends large amounts of UDP packets to random ports causing the target to repeatedly check and respond.
        
    - **SYN Flood:** Exploits the TCP handshake by sending many SYN requests without completing the handshake, exhausting server resources.
        

### 2. **Application Layer Attacks**

- **Description:** Target specific applications or services by sending legitimate-looking requests that consume server resources.
    
- **Example:** HTTP Flood, where many HTTP requests are sent to a web server to overload it.
    

### 3. **Protocol Attacks**

- **Description:** Exploit weaknesses in network protocols to consume server or network device resources.
    
- **Example:** Ping of Death, Smurf Attack, or Fragmentation attacks.
    

### 4. **Resource Exhaustion Attacks**

- **Description:** Exploit application or server resource limitations, like CPU, memory, or disk space.
    
- **Example:** Sending requests that cause heavy computation or large memory allocations.
    

### 5. **Distributed Denial of Service (DDoS)**

- **Description:** A large-scale DoS attack where multiple compromised systems (botnet) are used to flood the target, making defense more difficult.
    
- **Key Feature:** Traffic comes from many sources, hiding the attack origin and increasing volume.
    