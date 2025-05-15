---
created: 2025-05-15T11:07
updated: 2025-05-15T11:08
---
#### **Definition:**

**Public Key Infrastructure (PKI)** is a framework of policies, procedures, hardware, software, and people that is used to create, manage, distribute, use, store, and revoke digital certificates. It enables secure data transmission and authentication over insecure networks (such as the Internet) through the use of public key cryptography.

PKI ensures the **confidentiality, integrity, authenticity, and non-repudiation** of digital communications.

---

### **Components of PKI:**

1. **Certificate Authority (CA):**
    
    - A trusted entity that issues and digitally signs public key certificates.
        
    - Verifies the identity of entities (users, servers, organizations).
        
    - Examples: DigiCert, Let's Encrypt.
        
2. **Registration Authority (RA):**
    
    - Acts as a verifier for the CA before a certificate is issued.
        
    - Authenticates the identity of users and forwards verified requests to the CA.
        
3. **Public and Private Keys:**
    
    - PKI is based on **asymmetric cryptography**.
        
    - The **public key** is distributed to others, while the **private key** is kept secret.
        
    - The key pair is used for encryption, decryption, digital signing, and signature verification.
        
4. **Digital Certificates:**
    
    - Electronically binds a public key with the identity of the certificate holder.
        
    - Typically follows the **X.509** standard.
        
    - Contains details such as the subject name, issuer, validity period, and public key.
        
5. **Certificate Revocation List (CRL):**
    
    - A list maintained by the CA of certificates that have been revoked before their expiration date.
        
    - Helps prevent the use of compromised or invalid certificates.
        
6. **Online Certificate Status Protocol (OCSP):**
    
    - A protocol used to query the status of a digital certificate in real time.
        
    - Alternative to downloading entire CRLs.
        
7. **PKI-enabled Applications:**
    
    - Applications that utilize PKI for secure communication and authentication, such as:
        
        - Email encryption (S/MIME)
            
        - Secure web browsing (HTTPS with SSL/TLS)
            
        - Digital signatures
            
        - VPN access control
            

---

### **Conclusion:**

PKI plays a vital role in securing modern digital communications by managing encryption keys and digital certificates. Its components work together to ensure that data remains confidential, authenticated, and protected from tampering or fraud.