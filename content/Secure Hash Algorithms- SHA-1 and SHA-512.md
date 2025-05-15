#### **A. SHA-1 (Secure Hash Algorithm 1)**

- **Developed by**: NSA and published by NIST in 1995.
    
- **Digest Size**: 160 bits (20 bytes).
    
- **Input Size**: Arbitrary length (processed in 512-bit blocks).
    
- **Output**: 160-bit fixed hash value.
    

##### **Process:**

- The message is divided into 512-bit blocks.
    
- Each block goes through multiple rounds of processing involving logical functions, bitwise operations, and modular additions.
    
- Final output is a 160-bit digest.
    

##### **Security Status:**

- **Broken**: In 2017, a practical collision attack was demonstrated by Google and CWI Amsterdam.
    
- No longer considered secure for cryptographic purposes.
    

---

#### **B. SHA-512 (Part of SHA-2 Family)**

- **Developed by**: NSA and published by NIST in 2001.
    
- **Digest Size**: 512 bits (64 bytes).
    
- **Input Size**: Arbitrary length (processed in 1024-bit blocks).
    
- **Output**: 512-bit fixed hash value.
    

##### **Process:**

- Uses **64-bit words** and processes input in 1024-bit chunks.
    
- Involves **80 rounds** of mixing operations using logical functions, constants, and modular additions.
    
- Designed to resist known cryptographic attacks.
    

##### **Security Status:**

- **Secure**: As of today, SHA-512 remains secure and is widely recommended for high-security applications.

### **Conclusion**

A secure hash function ensures data **integrity, authenticity**, and **confidentiality**. While **SHA-1** is no longer suitable for secure systems due to vulnerability to collision attacks, **SHA-512** offers a high level of security and is widely adopted in modern cryptographic protocols.