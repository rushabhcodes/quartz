---
created: 2025-05-15T09:17
updated: 2025-05-15T09:17
---
### **X.509 Certificate Format**

The most widely used format for digital certificates is **X.509**, defined by the ITU-T standard. It is used in **SSL/TLS, HTTPS, S/MIME**, and many security protocols.

#### **Structure of X.509 Certificate:**

|**Field**|**Description**|
|---|---|
|**Version**|Indicates the version of X.509 (v1, v2, v3). Most commonly used is v3.|
|**Serial Number**|Unique number assigned by the CA to the certificate.|
|**Signature Algorithm**|Algorithm used by the CA to sign the certificate (e.g., SHA256 with RSA).|
|**Issuer**|Distinguished Name (DN) of the CA that issued the certificate.|
|**Validity Period**|Contains start and end dates (Not Before / Not After) for certificate validity.|
|**Subject**|DN of the entity to whom the certificate is issued (e.g., domain or person).|
|**Subject Public Key Info**|The public key and the algorithm used.|
|**Extensions** (v3 only)|Extra data like Subject Alternative Name (SAN), key usage, etc.|
|**Signature**|Digital signature by the CA over the certificate contents.|

---

### **Example (simplified)**

```
Certificate:
  Data:
    Version: 3 (0x2)
    Serial Number: 1234567890
    Signature Algorithm: sha256WithRSAEncryption
    Issuer: CN=Example CA, O=Certification Authority
    Validity:
        Not Before: Jan 1 00:00:00 2025 GMT
        Not After : Jan 1 00:00:00 2026 GMT
    Subject: CN=www.example.com, O=Example Corp
    Subject Public Key Info:
        Public Key Algorithm: rsaEncryption
            Public-Key: (2048 bit)
    Extensions:
        X509v3 Subject Alternative Name: 
            DNS:www.example.com, DNS:example.com
  Signature Algorithm: sha256WithRSAEncryption
      Signature: <encrypted hash>
```
