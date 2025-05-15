---
created: 2025-05-15T08:47
updated: 2025-05-15T08:48
---
## 🔥 **Firewall: Intro**

A **firewall** is a critical network security device or software that acts as a barrier between a trusted internal network and untrusted external networks such as the Internet. It monitors, filters, and controls network traffic based on a defined set of security rules to prevent unauthorized access and threats.

### **Purpose of a Firewall:**

- To **allow legitimate traffic** and block unauthorized or harmful traffic.
    
- Protect internal systems from external attacks.
    
- Enforce security policies by controlling data flow.
    
- Log and audit network traffic for security analysis.
    

---

## 🔸 **Types of Firewalls**

### 1. **Packet-Filtering Firewall**

- **Operation Layer:** Network Layer (Layer 3).
    
- **How it Works:** Examines each packet independently based on header information such as source IP address, destination IP address, source and destination ports, and protocol (TCP/UDP/ICMP).
    
- **Characteristics:**
    
    - Works on predefined rules (access control lists).
        
    - Does not track connection state (stateless).
        
    - Fast and efficient.
        
    - Limited security because it cannot inspect packet contents or establish connection context.
        
- **Use Case:** Basic filtering where speed is important, and threats are simple.
    

---

### 2. **Stateful Inspection Firewall**

- **Operation Layer:** Network and Transport Layers (Layer 3 and 4).
    
- **How it Works:** Tracks the **state of active connections** (TCP handshakes, UDP communication) and makes decisions based on the state of the connection (e.g., new, established, related).
    
- **Characteristics:**
    
    - Maintains a **state table** of all ongoing connections.
        
    - Filters packets based on both rules and connection state.
        
    - Provides more security than packet-filtering by preventing spoofed packets and unauthorized access.
        
    - Slightly slower than packet-filtering due to state maintenance.
        
- **Use Case:** Most common firewall type in enterprise networks due to balance of security and performance.
    

---

### 3. **Application Layer Firewall (Proxy Firewall)**

- **Operation Layer:** Application Layer (Layer 7).
    
- **How it Works:** Acts as an intermediary (proxy) between the user and the destination server. It inspects the actual content of the traffic (e.g., HTTP, FTP, SMTP), and can enforce application-specific rules.
    
- **Characteristics:**
    
    - Can block specific application commands or content.
        
    - Provides deep packet inspection.
        
    - Can detect and block malware or malicious payloads within the traffic.
        
    - Can filter web content (URLs, scripts).
        
    - Usually introduces latency because of deep inspection and proxying.
        
- **Use Case:** Protecting web servers, filtering email traffic, or enforcing strict application policies.
    

---

### 4. **Next-Generation Firewall (NGFW)**

- **Operation Layer:** Multiple layers including Application Layer.
    
- **How it Works:** Combines traditional firewall features with additional functionalities like:
    
    - Deep Packet Inspection (DPI).
        
    - Intrusion Prevention Systems (IPS).
        
    - Application awareness and control.
        
    - Malware detection.
        
    - User identity awareness.
        
- **Characteristics:**
    
    - Can detect sophisticated attacks, including zero-day threats.
        
    - Offers granular control over applications regardless of port or protocol.
        
    - Integrates with threat intelligence feeds.
        
    - Can perform SSL/TLS decryption for inspecting encrypted traffic.
        
- **Use Case:** Modern enterprise environments requiring advanced security beyond basic packet filtering.
    

---

### 5. **Circuit-Level Gateway**

- **Operation Layer:** Session Layer (Layer 5).
    
- **How it Works:** Monitors TCP handshakes and session establishment to ensure legitimacy. Once a session is established, packets flow without further inspection.
    
- **Characteristics:**
    
    - Does not inspect the contents of packets.
        
    - Focuses on session validation rather than data inspection.
        
    - Faster than application layer firewalls but less secure.
        
- **Use Case:** Situations requiring lightweight filtering with session validation.
    

---

## ⚔️ **Firewall Deployment Types**

- **Network-Based Firewalls:** Hardware devices placed at the network perimeter.
    
- **Host-Based Firewalls:** Software firewalls installed on individual devices to protect them locally.
    
- **Cloud Firewalls:** Firewalls as a service in cloud environments.
    

---

## Summary Table of Firewall Types

|Firewall Type|Layer(s) Operated|Key Features|Pros|Cons|
|---|---|---|---|---|
|Packet-Filtering|Network (Layer 3)|Filters by IP, ports, protocols|Fast, simple|No connection context|
|Stateful Inspection|Network & Transport (3-4)|Tracks connection states|More secure, connection-aware|Moderate overhead|
|Application Layer (Proxy)|Application (Layer 7)|Deep content inspection, application-aware|High security, granular control|Slower due to inspection|
|Next-Generation Firewall|Multiple including Layer 7|DPI, IPS, malware detection, user control|Advanced threat protection|Complex, resource intensive|
|Circuit-Level Gateway|Session (Layer 5)|Validates TCP sessions|Lightweight, fast|Limited inspection|
