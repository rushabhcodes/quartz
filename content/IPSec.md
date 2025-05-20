---
created: 2025-05-15T08:33
updated: 2025-05-16T08:10
---
## IPSec: Tunnel and Transport Modes with AH and ESP

IPSec is a set of protocols that secure internet communications by providing encryption and
authentication at the network layer (Layer 3) of the OSI model. It is used to establish secure
connections between network devices, such as routers, firewalls, and hosts.

IPSec ensures secure data transmission over networks by providing three key security functions:

- **Confidentiality** through encryption,
    
- **Integrity** through hashing,
    
- **Authentication** using keys or certificates,

---

## IPSec Modes of Operation

### 1. Tunnel Mode

- Encrypts the **entire IP packet** (header + payload).
    
- A **new IP header** is added.
    
- Commonly used in **network-to-network (site-to-site VPNs)**.
    

**Example:** Secure data exchange between two company branches over the internet.


| IP header | IPSec Header | IP header | protected data |
| --------- | ------------ | --------- | -------------- |

### 2. Transport Mode

- Encrypts **only the payload**; original IP header remains.
    
- Suitable for **host-to-host communication** with lower overhead.
    

**Example:** Secure communication between two servers within a private network.

| IP header | IPSec Header | protected data |
| --------- | ------------ | -------------- |

![[Transport Mode and Tunnel Mode.excalidraw.svg]]

---

## Tunnel vs Transport Mode

|Feature|Tunnel Mode|Transport Mode|
|---|---|---|
|Encryption|Header + Payload|Payload only|
|IP Header|Replaced with a new one|Original header retained|
|Use Case|Network-to-network (VPN)|Host-to-host|
|Overhead|Higher|Lower|
|Privacy|Full packet concealment|Header remains visible|

---

## IPSec Protocols: AH vs ESP

### AH (Authentication Header)

- Provides **integrity and authentication**.
    
- **No encryption**; IP header and payload are protected.
    
- Used when **confidentiality is not required**.
    

### ESP (Encapsulating Security Payload)

- Provides **encryption**, **authentication**, and **integrity**.
    
- Primarily protects the **payload**.
    
- More widely used than AH due to support for confidentiality.
    


---
## **Applications of IPSec**

1. **Virtual Private Networks (VPNs)**
    
    - Secure remote access for users over the internet.
        
2. **Site-to-Site Connectivity**
    
    - Secure communication between two networks (e.g., branch offices).
        
3. **Secure Communication in IPv6**
    
    - IPSec is **mandatory** in IPv6 for encryption and authentication.
        
4. **Secure E-commerce Transactions**
    
5. **Secure Data Exchange Between Servers**
    

---

## **Advantages of IPSec**

- **Strong Security** – Provides confidentiality, integrity, and authentication.
    
- **Transparent to Applications** – Works at the network layer, so no need to modify applications.
    
- **Supports Multiple Encryption Algorithms** – Such as AES, 3DES.
    
- **Scalability** – Suitable for small and large networks.
    
- **Standards-Based** – Interoperable across devices and platforms.
    
- **Protects All IP Traffic** – Unlike SSL/TLS, which protects only specific applications.
    

---
## Conclusion

IPSec secures IP communications using **Tunnel Mode** (for network-level VPNs) and **Transport Mode** (for host-to-host links). It relies on **AH** and **ESP** for authentication, integrity, and optionally confidentiality, depending on the security requirements.