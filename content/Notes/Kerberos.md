---
created: 2025-05-15T11:12
updated: 2025-05-15T21:01
---
Kerberos is a **network authentication protocol** developed by MIT, designed to provide strong authentication for client-server applications using secret-key cryptography. It allows nodes (users and services) to prove their identity securely over a non-secure network.

---

### **Key Concepts of Kerberos**

1. **Authentication** – Verifying the identity of a user or service.
    
2. **Tickets** – Used to prove identity without sending passwords over the network.
    
3. **Trusted Third Party** – A central authority called the **Key Distribution Center (KDC)** issues tickets.
    
4. **Symmetric Encryption** – Kerberos uses secret-key cryptography (e.g., AES, DES).
    

---

### **Components of Kerberos**

1. **Client** – The user or application that wants to access a service.
    
2. **Application Server (Service Server)** – The server hosting the desired service.
    
3. **KDC (Key Distribution Center)** – Consists of:
    
    - **Authentication Server (AS)** – Verifies the user and provides a Ticket Granting Ticket (TGT).
        
    - **Ticket Granting Server (TGS)** – Issues service tickets based on the TGT.
        

---

### **Kerberos Authentication Process**

Here’s a step-by-step explanation of the Kerberos workflow:

#### **1. User Login and Authentication**

- The user logs in and sends a request to the **Authentication Server (AS)** with their username.
    
- The AS checks if the user exists and sends back:
    
    - A **Ticket Granting Ticket (TGT)** encrypted with the TGS’s key.
        
    - A **session key** encrypted with the user’s password-derived key.
        

#### **2. Requesting Access to Service**

- The user decrypts the session key using their password.
    
- They send the TGT and an **Authenticator** (containing a timestamp and client ID, encrypted with the session key) to the **Ticket Granting Server (TGS)**.
    
- The TGS verifies the TGT and Authenticator, then sends back:
    
    - A **Service Ticket** encrypted with the service server's secret key.
        
    - A **session key** for the client-server communication.
        

#### **3. Accessing the Service**

- The client sends the Service Ticket and a new Authenticator (now using the service session key) to the application server.
    
- The server verifies both and may optionally reply with a timestamp to confirm mutual authentication.
    
- The client is now authenticated and can use the service securely.
    

---

### **Diagram**
![[Drawing 2025-05-15 20.53.39.excalidraw.svg]]


---

### **Advantages of Kerberos**

- **No passwords transmitted** across the network.
- **Mutual authentication** between client and server.
- **Single Sign-On (SSO)** capability.
- **Scalability** across large distributed systems.

---

### **Limitations**

- Requires **synchronized clocks** between nodes.
- If the **KDC is compromised**, the entire system is vulnerable.
- Initial setup and key management can be **complex**.

---

### **Conclusion**

Kerberos is a robust and widely-used authentication protocol, essential for secure communication in distributed environments. By using tickets and symmetric key encryption, it effectively reduces the risk of password theft and impersonation attacks.