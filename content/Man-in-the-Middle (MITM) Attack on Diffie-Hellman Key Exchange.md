---
created: 2025-05-15T11:01
updated: 2025-05-15T11:04
---
#### **MITM Attack on Diffie-Hellman:**

In a **Man-in-the-Middle attack**, an attacker (say, Mallory) intercepts and alters the messages between Alice and Bob:

1. Alice sends her public key `A` to Bob.
    
2. Mallory intercepts `A` and sends her own key `M1 = g^m1 mod p` to Bob.
    
3. Bob replies with his key `B`, which Mallory intercepts and replaces with her key `M2 = g^m2 mod p` and sends it to Alice.
    
4. Now:
    
    - Alice computes a shared key with `M2`, thinking it's Bob's key.
        
    - Bob computes a shared key with `M1`, thinking it's Alice's key.
        
    - Mallory computes both shared keys (with `m1` and `m2`) and can now **decrypt, read, modify, and re-encrypt messages** between Alice and Bob without their knowledge.
        

Thus, **Mallory has successfully positioned herself between Alice and Bob**, undermining the confidentiality of the communication.

---

#### **How to Prevent MITM in Diffie-Hellman:**

To overcome this vulnerability, authentication mechanisms must be employed along with the Diffie-Hellman protocol:

---

##### **1. Digital Signatures:**

- Alice and Bob sign their public values using their private keys.
    
- These signatures are verified by the other party using the sender's public key.
    
- Even if an attacker intercepts and replaces values, they cannot forge valid signatures without the private keys.
    

---

##### **2. Public Key Infrastructure (PKI):**

- Use certificates issued by trusted Certificate Authorities (CAs) to authenticate public keys.
    
- Ensures that the key really belongs to the stated entity.
    

---

##### **3. Use of Authenticated Diffie-Hellman (e.g., STS Protocol):**

- The **Station-to-Station (STS)** protocol combines DH key exchange with public key signatures and encryption to provide mutual authentication and protect against MITM.
    

---

##### **4. Use of Pre-Shared Keys (PSK):**

- In environments where both parties know a shared secret ahead of time, DH values can be authenticated using Message Authentication Codes (MACs) based on the PSK.
    

---

#### **Conclusion:**

While the standard **Diffie-Hellman protocol provides secure key exchange**, it is inherently **vulnerable to man-in-the-middle attacks** if not combined with an authentication mechanism. **To prevent MITM attacks**, it is essential to integrate **digital signatures, PKI, or authenticated DH variants**.