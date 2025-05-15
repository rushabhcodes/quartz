---
created: 2025-05-15T10:09
updated: 2025-05-15T10:10
---
### **1. Definitions**

#### **Non-Repudiation:**

Non-repudiation is a security principle that ensures **a sender cannot deny having sent a message** and **a receiver cannot deny having received it**. It provides **proof of origin, delivery, and integrity** of data, preventing either party from denying their actions in a communication.

#### **Authentication:**

Authentication is the process of **verifying the identity of a user, system, or entity** before allowing access to a system or data. It ensures that the entity is **who it claims to be**.

---

### **2. How Non-Repudiation and Authentication are Achieved**

Both can be achieved using **digital signatures** and **public key cryptography**.

#### **Mechanism:**

|**Technique**|**Purpose**|
|---|---|
|**Digital Signature**|Provides non-repudiation|
|**Public Key Encryption**|Provides authentication and confidentiality|

---

### **3. Example Using Public Key Infrastructure (PKI)**

Let’s consider two parties: **Alice (Sender)** and **Bob (Receiver)**.

#### **Step-by-Step Process:**

1. **Authentication:**
    
    - Bob wants to ensure that the message he received is truly from Alice.
        
    - Alice **digitally signs** the message using her **private key**.
        
    - Bob uses **Alice's public key** to verify the signature.
        
    - If verification succeeds, it confirms **Alice's identity** (Authentication).
        
2. **Non-Repudiation:**
    
    - Since only Alice has access to her private key, **she cannot deny having sent** the message.
        
    - The signature acts as **evidence** in case of a dispute.
        

---

### **4. Example in Practice (Pseudocode):**

```python
// Alice signs the message
Message = "Project submitted"
Signature = Sign(Message, Alice_PrivateKey)

// Alice sends (Message + Signature) to Bob

// Bob verifies
IsValid = Verify(Message, Signature, Alice_PublicKey)

If IsValid:
    Print("Message is authentic and non-repudiable")
Else:
    Print("Message verification failed")
```

---

### **5. Conclusion**

Non-repudiation ensures that senders cannot deny their messages, while authentication ensures that entities are correctly identified. These security objectives are crucial in digital communications and are effectively achieved through cryptographic techniques like **digital signatures** and **public key cryptography**.