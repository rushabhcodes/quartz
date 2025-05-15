---
created: 2025-05-15T11:09
updated: 2025-05-15T11:09
---
#### **Definition:**

The **Advanced Encryption Standard (AES)** is a **symmetric block cipher** used for encrypting and decrypting data securely. It was established as the **encryption standard** by the U.S. National Institute of Standards and Technology (NIST) in **2001**, replacing the older **Data Encryption Standard (DES)** due to its vulnerability to brute-force attacks.

AES is based on the **Rijndael algorithm**, developed by **Joan Daemen and Vincent Rijmen**.

---

### **Key Features of AES:**

- **Block size:** 128 bits
    
- **Key sizes:** 128, 192, or 256 bits
    
- **Symmetric encryption:** Uses the same key for both encryption and decryption
    
- **Rounds:**
    
    - 10 rounds for 128-bit keys
        
    - 12 rounds for 192-bit keys
        
    - 14 rounds for 256-bit keys
        

---

### **AES Structure:**

AES operates on a **4×4 byte matrix** called the **state**. The data is encrypted in a series of rounds that involve several well-defined transformations:

---

#### **AES Operations Per Round:**

1. **SubBytes (Substitution):**
    
    - Each byte in the state is replaced with a corresponding value from the **S-Box** (substitution box), a nonlinear substitution table.
        
2. **ShiftRows (Permutation):**
    
    - Rows of the state matrix are **shifted cyclically** to the left by different offsets to achieve diffusion.
        
3. **MixColumns (Mixing):**
    
    - Each column of the state is transformed using a **fixed polynomial** over the finite field GF(2⁸). This step ensures interdependence between the bytes of a column.
        
4. **AddRoundKey (Key Mixing):**
    
    - The current state is XORed with a portion of the expanded key (called the round key).
        

> Note: The **final round** does **not** include the MixColumns step.

---

### **AES Key Expansion:**

The original cipher key is expanded into a series of round keys using a key schedule. This is required because each round of AES uses a different key derived from the main key.

---

### **AES Encryption Process:**

```text
Initial Round:
    AddRoundKey

Rounds (Repeated 9/11/13 times based on key size):
    SubBytes
    ShiftRows
    MixColumns
    AddRoundKey

Final Round:
    SubBytes
    ShiftRows
    AddRoundKey
```

---

### **Security of AES:**

- AES is considered **highly secure** and is used worldwide for encrypting sensitive data, including government and military applications.
    
- It resists all known practical cryptographic attacks, including:
    
    - Brute-force attacks (due to large key size)
        
    - Linear and differential cryptanalysis
        

---

### **Applications of AES:**

- Secure network communications (e.g., HTTPS, VPNs)
    
- Disk and file encryption (e.g., BitLocker, VeraCrypt)
    
- Secure messaging and voice applications
    
- Wireless security (e.g., WPA2 for Wi-Fi)
    

---

### **Conclusion:**

AES is a powerful, efficient, and secure encryption standard that meets the demands of modern-day data protection. Its structure and operations ensure both **confidentiality** and **performance**, making it the de facto standard in symmetric encryption.