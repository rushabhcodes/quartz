---
created: 2025-05-10T10:50
updated: 2025-05-15T11:06
---
#### **Introduction:**

A **block cipher** is a symmetric key cipher which encrypts data in fixed-size blocks (e.g., 64-bit or 128-bit blocks). To encrypt messages longer than a single block or of arbitrary size, **modes of operation** are employed. These modes define how blocks are linked and processed to ensure confidentiality and sometimes integrity.

Common block ciphers include **AES**, **DES**, and **Blowfish**. However, the cipher alone is not sufficient; the _mode of operation_ plays a crucial role in the overall security of the encryption.

---

### **Common Modes of Operation:**

---

#### **1. Electronic Codebook (ECB):**

- **Description**: Each block is encrypted independently.
    
- **Encryption**:  
    `Ci = E(K, Pi)`
    
- **Decryption**:  
    `Pi = D(K, Ci)`
    
- **Advantages**:
    
    - Simple and fast.
        
- **Disadvantages**:
    
    - Identical plaintext blocks produce identical ciphertext blocks.
        
    - Pattern leakage; not secure for long or repetitive data.
        

> **Use Case**: Not recommended for general use. Suitable only for small, non-repetitive, and random data.

---

#### **2. Cipher Block Chaining (CBC):**

- **Description**: Each plaintext block is XORed with the previous ciphertext block before encryption.
    
- **Encryption**:
    
    - `C0 = E(K, P0 ⊕ IV)`
        
    - `Ci = E(K, Pi ⊕ Ci−1)`
        
- **Decryption**:
    
    - `Pi = D(K, Ci) ⊕ Ci−1`
        
- **Advantages**:
    
    - Prevents pattern leakage.
        
- **Disadvantages**:
    
    - Requires padding.
        
    - Sequential; cannot be parallelized.
        
    - Needs an unpredictable IV (Initialization Vector).
        

> **Use Case**: Secure file encryption.

---

#### **3. Cipher Feedback (CFB):**

- **Description**: Converts block cipher into a stream cipher.
    
- **Encryption**:
    
    - `Ci = Pi ⊕ E(K, Ci−1)` (with IV as C0)
        
- **Decryption**:
    
    - `Pi = Ci ⊕ E(K, Ci−1)`
        
- **Advantages**:
    
    - Self-synchronizing.
        
    - No padding required.
        
- **Disadvantages**:
    
    - Still sequential.
        
    - Slightly slower than stream ciphers.
        

> **Use Case**: Real-time streaming encryption.

---

#### **4. Output Feedback (OFB):**

- **Description**: Uses the block cipher output as keystream.
    
- **Encryption/Decryption**:
    
    - `Oi = E(K, Oi−1)` (with O0 = IV)
        
    - `Ci = Pi ⊕ Oi`
        
    - `Pi = Ci ⊕ Oi`
        
- **Advantages**:
    
    - Errors do not propagate.
        
    - Can be precomputed.
        
- **Disadvantages**:
    
    - If IV is reused, security is compromised.
        

> **Use Case**: Error-prone transmission media.

---

#### **5. Counter Mode (CTR):**

- **Description**: Turns block cipher into a stream cipher using a counter.
    
- **Encryption/Decryption**:
    
    - `Ci = Pi ⊕ E(K, Counter + i)`
        
    - `Pi = Ci ⊕ E(K, Counter + i)`
        
- **Advantages**:
    
    - Fast and parallelizable.
        
    - No error propagation.
        
    - No padding needed.
        
- **Disadvantages**:
    
    - Reusing counter/IV is fatal to security.
        

> **Use Case**: High-performance encryption (e.g., disk encryption, network traffic).

---

### **Comparison Table:**

|Mode|Parallelizable|Error Propagation|Padding Required|IV Needed|
|---|---|---|---|---|
|ECB|Yes|No|Yes|No|
|CBC|No|Yes (1 block)|Yes|Yes|
|CFB|No|Yes (1 block)|No|Yes|
|OFB|Yes|No|No|Yes|
|CTR|Yes|No|No|Yes|

---

### **Conclusion:**

Block cipher modes of operation enhance the utility and security of basic block ciphers. The choice of mode depends on the specific application and requirements such as error resilience, parallelism, and data size. Among modern applications, **CBC** is widely used for general encryption, while **CTR** and **OFB** are preferred in high-speed or real-time systems.