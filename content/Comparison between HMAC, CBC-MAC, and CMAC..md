---
created: 2025-05-15T10:46
updated: 2025-05-15T10:47
---
|**Aspect**|**HMAC**|**CBC-MAC**|**CMAC**|
|---|---|---|---|
|**Full Form**|Hash-based Message Authentication Code|Cipher Block Chaining Message Auth. Code|Cipher-based Message Authentication Code|
|**Underlying Primitive**|Cryptographic Hash Function (e.g., SHA-1, SHA-256)|Block Cipher (e.g., AES, DES)|Block Cipher (e.g., AES)|
|**Key Input**|Single secret key|Single secret key|Single secret key|
|**Security Dependency**|Depends on the security of the hash function|Depends on block cipher and proper implementation|More secure variant of CBC-MAC|
|**Variable-Length Messages**|Secure for all message lengths|**Insecure** for variable-length messages|**Secure** for variable-length messages|
|**Padding Requirement**|Uses inner/outer padding for hash input|Requires message padding to full blocks|Requires message padding and subkey derivation|
|**Standardization**|RFC 2104|ISO/IEC 9797-1|NIST SP 800-38B|
|**Performance**|High efficiency with hash functions|Efficient, but limited to fixed-length messages|Efficient and secure for all lengths|
|**Use Cases**|TLS, IPsec, digital signatures|Legacy systems, embedded systems|Replacement for CBC-MAC in secure systems|
### **Summary**

- **HMAC** is widely used, versatile, and secure for all message lengths using hash functions.
    
- **CBC-MAC** is simple and efficient but **insecure** for variable-length messages unless precautions are taken.
    
- **CMAC** improves upon CBC-MAC by being secure for messages of any length and is based on block ciphers like AES.
    

For modern cryptographic applications, **CMAC** is preferred over CBC-MAC, and **HMAC** remains a popular choice due to its simplicity and strength based on hash functions.