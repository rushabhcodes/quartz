## IPSec: Tunnel and Transport Modes with AH and ESP

**IPSec (Internet Protocol Security)** is a protocol suite that secures IP communication by providing:

- **Confidentiality** through encryption,
    
- **Integrity** through hashing,
    
- **Authentication** using keys or certificates,
    
- **Anti-replay protection** via sequence numbers.
    

---

## Modes of Operation

### 1. Tunnel Mode

- Encrypts the **entire IP packet** (header + payload).
    
- A **new IP header** is added.
    
- Commonly used in **network-to-network (site-to-site VPNs)**.
    

**Example:** Secure data exchange between two company branches over the internet.

### 2. Transport Mode

- Encrypts **only the payload**; original IP header remains.
    
- Suitable for **host-to-host communication** with lower overhead.
    

**Example:** Secure communication between two servers within a private network.

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

## Security Functions Provided by IPSec

- **Authentication:** Confirms sender identity.
    
- **Integrity:** Detects modifications.
    
- **Confidentiality:** Prevents unauthorized access (via ESP).
    
- **Anti-replay:** Prevents duplicate packet attacks.
    

---

## Conclusion

IPSec secures IP communications using **Tunnel Mode** (for network-level VPNs) and **Transport Mode** (for host-to-host links). It relies on **AH** and **ESP** for authentication, integrity, and optionally confidentiality, depending on the security requirements.