---
created: 2025-05-19T16:59
updated: 2025-05-19T19:05
---
![[Pasted image 20250519190134.png]]

**Entities Involved:**

- **MN (Mobile Node):** Your device that's moving.
- **CN (Correspondent Node):** The device MN is talking to.
- **HA (Home Agent):** The router on MN's home network.
- **FA (Foreign Agent):** The router on the network MN is visiting.
- **CoA (Care-of Address):** MN's temporary address in the foreign network.

---

**A. Packet Delivery TO the Mobile Node (from CN to MN)**

Imagine the arrows showing the data flow. (See diagrams on page 31 and page 33 )

1. **CN → HA (Packet to Home Network)**
    
    - The CN sends a packet.
        - **Destination IP:** MN's permanent Home Address.
        - **Source IP:** CN's Address.
    - `CN ===> Internet ===> HA`
    - This packet travels through the internet and, using standard routing, arrives at the MN's Home Network, where the HA intercepts it (often using Proxy ARP). The HA knows the MN is not at home.
        
2. **HA → FA (Tunneling to Foreign Network)**
    
    - The HA takes the original packet from the CN.
    - It encapsulates this original packet inside a _new_ IP packet. This is called tunneling.
        
        - **Outer (New) Header - Source IP:** HA's Address.
        - **Outer (New) Header - Destination IP:** MN's current Care-of Address (COA), which is often the FA's address.
            
        - **Inner (Original) Header - Source IP:** CN's Address.
        - **Inner (Original) Header - Destination IP:** MN's Home Address.
    - `HA ====> (Tunnel through Internet) ====> FA`
    - The HA sends this encapsulated packet to the FA.
        
3. **FA → MN (Delivery in Foreign Network)**
    
    - The FA receives the encapsulated packet from the HA.
    - The FA decapsulates it, removing the outer header and retrieving the original packet.
        
    - The FA now sees the original packet (Destination IP: MN's Home Address; Source IP: CN's Address).
    - `FA ===> MN`
    - The FA forwards this original packet to the MN on the foreign network.
        

---

**B. Packet Delivery FROM the Mobile Node (MN to CN)**

Imagine the arrows for the return path. (See diagram on page 32 )

1. **MN → FA → CN (Directly to Correspondent Node)**
    - The MN wants to send a packet to the CN.
        - **Source IP:** MN's permanent Home Address.
        - **Destination IP:** CN's Address.
    - `MN ===> FA ===> Internet ===> CN`
    - The MN sends the packet. Typically, the FA acts as the MN's default router in the foreign network.
        
    - The FA receives the packet from the MN and routes it normally through the internet towards the CN. The packet does not necessarily need to go through the HA in this direction (unless reverse tunneling is used, which is an optimization).
        
