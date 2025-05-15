
## Introduction to PGP (Pretty Good Privacy)

**PGP (Pretty Good Privacy)** is a **data encryption and decryption** program that provides **confidentiality**, **authentication**, and **integrity** for digital communication—primarily emails.

Developed by **Phil Zimmermann in 1991**, PGP became widely popular for securing emails and files against unauthorized access.

---

## Purpose of PGP

PGP is used to:

- **Encrypt messages** so only the intended recipient can read them.
    
- **Digitally sign messages** to verify the sender and detect tampering.
    
- **Compress data** before encryption to reduce size and increase security.
    
- **Ensure end-to-end security** in email communication.
    

---

## How PGP Works (Basic Overview)

PGP uses **hybrid cryptography**:

- **Symmetric encryption** (e.g., AES) for encrypting the actual message.
    
- **Asymmetric encryption** (e.g., RSA) for encrypting the symmetric session key.
    
- **Hash functions** (e.g., SHA) for creating message digests to ensure integrity.
    

---

## Key Concepts in PGP

- **Public and Private Keys:** Each user has a key pair for encryption and signing.
    
- **Digital Signature:** Proves the message is from the claimed sender.
    
- **Session Key:** A randomly generated key used for encrypting a specific message.
    
- **Key Rings:** Databases that store public keys (from others) and private keys (your own).
    

---

## ✅ Features of PGP

|Feature|Description|
|---|---|
|Confidentiality|Only intended recipients can decrypt the message|
|Authentication|Verifies the sender using digital signatures|
|Integrity|Detects any change in the message|
|Non-repudiation|Sender cannot deny sending a digitally signed message|
|Key Management|Uses key rings to store and trust public/private keys|

---

## How PGP Achieves Confidentiality and Authentication in Emails

**PGP** uses a combination of **symmetric and asymmetric encryption** to secure email communication.

### 1. **Confidentiality**

- Ensures **only the intended recipient** can read the email.
    
- Steps:
    
    1. A **random session key** is generated.
        
    2. The email is **encrypted using the session key** (symmetric encryption, e.g., AES).
        
    3. The session key is then **encrypted using the recipient’s public key** (asymmetric encryption, e.g., RSA).
        
    4. The encrypted session key + encrypted message are sent to the recipient.
        
    5. The recipient uses their **private key to decrypt the session key**, then uses that session key to decrypt the message.
        

### 2. **Authentication**

- Ensures the **sender is genuine** and the message is **untampered**.
    
- Steps:
    
    1. The sender creates a **hash (digest)** of the message.
        
    2. The hash is **digitally signed** using the sender’s **private key**.
        
    3. The recipient uses the **sender’s public key** to verify the signature.
        
    4. If verification is successful, it confirms **authenticity** and **integrity**.
        

---

## Key Rings in PGP

PGP uses **key rings** to manage public and private keys:

### 1. **Public Key Ring**

- Stores **trusted public keys** of other users.
    
- Used to **encrypt messages** or verify **signatures**.
    
- Helps ensure the recipient’s identity through a **web of trust** model.
    

### 2. **Private Key Ring**

- Stores the user’s **own private keys**.
    
- Used to **decrypt received messages** or **sign** outgoing messages.
    
- Usually **protected with a passphrase** to prevent unauthorized use.
    

---

### Summary

|Feature|How PGP Achieves It|
|---|---|
|Confidentiality|Encrypts message with a symmetric key, which is then encrypted with recipient's public key|
|Authentication|Signs message hash with sender's private key; verified using public key|
|Key Management|Key rings store and manage public/private keys|
