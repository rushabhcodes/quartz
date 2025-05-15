### **What is a Replay Attack?**

A **replay attack** is a type of network attack in which a valid data transmission is maliciously captured and retransmitted by an attacker. The goal is to **trick the recipient into thinking the message is legitimate and original**, thereby gaining unauthorized access or triggering unintended actions.

Replay attacks exploit the **lack of freshness** in communication. Since the data is originally valid, systems that do not verify message uniqueness or timing can be easily fooled.

---

### **Examples of Replay Attacks**

1. **Login Replay**
    
    - An attacker captures a user's login request (e.g., token or encrypted credentials) and replays it later to access the system without needing the password.
        
2. **Online Payments**
    
    - A payment authorization message is intercepted and replayed to make multiple unauthorized charges to the same account.
        
3. **RFID Access Systems**
    
    - An attacker clones the radio signal from a valid RFID badge and reuses it to open secure doors.
        

---

### **Three General Strategies to Prevent Replay Attacks**

1. **Timestamps**
    
    - Attach the current time to each message.
        
    - The receiver accepts messages only if they fall within an acceptable time window.
        
    - Ensures the message is recent and cannot be reused later.
        
2. **Nonces (Number Used Once)**
    
    - A random, one-time-use value is included in each message.
        
    - The server tracks nonces and rejects duplicates.
        
    - Prevents reuse of previously sent messages.
        
3. **Sequence Numbers / Session Tokens**
    
    - Each message in a session is labeled with a unique sequence number.
        
    - If a number is reused or out of order, the message is rejected.
        
    - Commonly used in secure protocols like SSL/TLS.
        

---

### **Conclusion**

Replay attacks take advantage of repeated use of legitimate data. They are **easy to perform** but can be **effectively prevented** using methods that ensure **message freshness and uniqueness**, such as **nonces, timestamps, and sequence numbers**. These are essential components of modern secure communication protocols.