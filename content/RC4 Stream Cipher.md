#### **Definition:**

**RC4** (Rivest Cipher 4 or Ron’s Code 4) is a widely used **symmetric key stream cipher** designed by **Ron Rivest** in 1987 for RSA Security. It was one of the most popular stream ciphers due to its simplicity and speed in software implementations.

RC4 generates a **pseudorandom stream of bits (keystream)**, which is **XORed** with the plaintext to produce ciphertext. The same process is used for decryption.

---

### **Key Characteristics:**

- **Type:** Stream cipher
    
- **Key size:** Typically 40 to 2048 bits
    
- **Operation:** Byte-oriented
    
- **Encryption and decryption:** Identical (due to XOR operation)
    
- **Speed:** High-speed performance in software
    

---

### **Components of RC4:**

1. **Key Scheduling Algorithm (KSA):**
    
    - Initializes a 256-byte array `S` using a variable-length key.
        
    - Produces a scrambled initial permutation of S.
        
2. **Pseudo-Random Generation Algorithm (PRGA):**
    
    - Uses the scrambled `S` array to generate a **keystream**.
        
    - The keystream is XORed with the plaintext (or ciphertext) to perform encryption or decryption.
        

---

### **Working of RC4:**

#### **1. Key Scheduling Algorithm (KSA):**

```c
for i = 0 to 255:
    S[i] = i
j = 0
for i = 0 to 255:
    j = (j + S[i] + key[i % keylength]) % 256
    swap S[i], S[j]
```

#### **2. Pseudo-Random Generation Algorithm (PRGA):**

```c
i = 0
j = 0
while generating keystream:
    i = (i + 1) % 256
    j = (j + S[i]) % 256
    swap S[i], S[j]
    t = (S[i] + S[j]) % 256
    keystream byte = S[t]
```

#### **3. Encryption/Decryption:**

```text
ciphertext = plaintext ⊕ keystream
plaintext = ciphertext ⊕ keystream
```

---

### **Example (Simplified):**

Suppose:

- Key = {1, 2, 3}
    
- Plaintext = {65, 66, 67}
    

RC4 would:

1. Initialize `S` with the key via KSA.
    
2. Generate keystream bytes.
    
3. XOR plaintext with keystream to produce ciphertext.
    

---

### **Security Issues:**

- **Key scheduling weaknesses:** The first few bytes of the keystream are biased, making RC4 vulnerable to attacks like Fluhrer, Mantin, and Shamir (FMS) attack.
    
- **Not secure for modern use:** RC4 is **deprecated** by organizations like **IETF** and **Microsoft** due to vulnerabilities.
    
- **Insecure in TLS and WEP:** Usage in **WEP** (Wired Equivalent Privacy) and older **TLS** versions has led to known cryptographic attacks.
    

---

### **Conclusion:**

RC4 is a fast and simple stream cipher that played a significant historical role in cryptography. However, due to multiple vulnerabilities and biases in its keystream, **RC4 is no longer considered secure** and should be avoided in modern applications. More secure alternatives like **ChaCha20** or **AES in CTR mode** are recommended today.