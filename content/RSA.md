---
created: 2025-05-15T11:13
updated: 2025-05-15T11:14
---
### **Introduction:**

**RSA** (Rivest-Shamir-Adleman) is one of the first public-key cryptosystems and is widely used for **secure data transmission**. It is based on the mathematical properties of large prime numbers and the difficulty of factoring large integers. RSA is used for both **encryption** and **digital signatures**.

---

### **Key Concepts in RSA:**

- **Asymmetric cryptography:** Uses a **pair of keys**—a public key for encryption and a private key for decryption.
    
- **Security basis:** Relies on the computational difficulty of factoring the product of two large prime numbers.
    

---

### **RSA Key Generation Steps:**

1. **Choose two distinct prime numbers**  
    Let `p` and `q` be two large primes.
    
2. **Compute `n = p × q`**  
    `n` is used as the **modulus** for both the public and private keys.
    
3. **Compute Euler’s totient function**  
    `φ(n) = (p − 1) × (q − 1)`
    
4. **Choose public exponent `e`**  
    Select `e` such that `1 < e < φ(n)` and `gcd(e, φ(n)) = 1`
    
5. **Compute private exponent `d`**  
    Find `d` such that `d × e ≡ 1 (mod φ(n))`  
    That is, `d` is the modular multiplicative inverse of `e` modulo `φ(n)`
    
6. **Public key = (e, n)**  
    **Private key = (d, n)**
    

---

### **RSA Encryption:**

To encrypt a message `M` (converted to integer):

$C = M^e \mod n$

Where:

- `C` is the ciphertext
    
- `M` is the plaintext
    
- `e` and `n` are from the recipient’s public key
    

---

### **RSA Decryption:**

To decrypt the ciphertext `C`:

M=Cdmod  nM = C^d \mod n

Where:

- `d` is the private key
    
- `n` is the modulus
    

---

### **Example (Small Numbers for Simplicity):**

1. Choose `p = 61`, `q = 53`  
    ⇒ `n = 61 × 53 = 3233`  
    ⇒ `φ(n) = (61−1)(53−1) = 3120`
    
2. Choose `e = 17` (common choice; gcd(17, 3120) = 1)
    
3. Compute `d` such that `d × 17 ≡ 1 (mod 3120)`  
    ⇒ `d = 2753`
    
4. Public Key = (17, 3233), Private Key = (2753, 3233)
    
5. Encrypt `M = 123`  
    ⇒ `C = 123^17 mod 3233 = 855`
    
6. Decrypt `C = 855`  
    ⇒ `M = 855^2753 mod 3233 = 123`
    

---

### **Applications of RSA:**

- Secure transmission of data over the internet
    
- Digital signatures and certificates
    
- Secure email (e.g., PGP)
    
- SSL/TLS handshake in HTTPS
    

---

### **Security of RSA:**

RSA’s security depends on:

- The size of the primes `p` and `q`
    
- Difficulty of **integer factorization**
    
- Proper key length (e.g., 2048-bit or higher in practice)
    

---

### **Conclusion:**

RSA is a powerful and widely adopted public-key cryptographic algorithm. Its ability to support **confidentiality**, **integrity**, and **authenticity** makes it a foundational component in modern security systems.