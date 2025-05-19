---
created: 2025-05-19T23:50
updated: 2025-05-19T23:50
---
### Equipment Identity Register (EIR)

The EIR is a database that maintains records of mobile devices based on their **IMEI** (International Mobile Equipment Identity) numbers.

**Functions of EIR:**

- **Device Authentication:**  
    Verifies the IMEI of a mobile device before allowing it to connect to the network.
    
- **Maintaining Device Lists:**
    
    - **Whitelist:** Devices allowed to access the network.
        
    - **Greylist:** Devices under monitoring (e.g., malfunctioning or suspicious devices).
        
    - **Blacklist:** Devices banned from the network due to theft, fraud, or other issues.
        

---

### Home Location Register (HLR)

The HLR is a central database that stores **permanent subscriber information** required for authentication, call routing, and roaming. It works in coordination with the **VLR (Visitor Location Register)** and **MSC (Mobile Switching Centre)** to track and manage users.

**Functions of HLR:**

- **Subscriber Information Storage:**  
    Maintains IMSI (International Mobile Subscriber Identity), MSISDN (phone number), service subscriptions, and authentication keys.
    
- **Location Management:**  
    Keeps track of the current location of subscribers by storing the identity of the VLR where they are currently registered.
    
- **Authentication and Security:**  
    Works with the AuC (Authentication Centre) to verify subscribers and prevent unauthorized access to the network.
    