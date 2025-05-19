---
created: 2025-05-19T23:00
updated: 2025-05-19T23:02
---
## **Wi-Fi Security Protocols**

Wi-Fi security protocols are encryption standards used to secure data transmitted over wireless networks. Over the years, several protocols have been developed, each offering improvements over its predecessor.

---

### 1. **WEP (Wired Equivalent Privacy)**

- **Introduced**: 1997 (as part of the original IEEE 802.11 standard)
    
- **Encryption**: RC4 stream cipher
    
- **Key Length**: 40-bit (original), extended to 104-bit
    

#### 🔹 Features:

- Designed to provide confidentiality comparable to wired networks.
    
- Uses static keys for encryption.
    

#### 🔻 Weaknesses:

- Vulnerable to several attacks (e.g., IV reuse, key cracking).
    
- Easily broken using tools like Aircrack-ng.
    
- **No longer considered secure**.
    

---

### 2. **WPA (Wi-Fi Protected Access)**

- **Introduced**: 2003 (as a temporary replacement for WEP)
    
- **Encryption**: TKIP (Temporal Key Integrity Protocol)
    
- **Key Management**: Dynamic key generation
    

#### 🔹 Features:

- Introduced message integrity checks.
    
- Uses per-packet key mixing to avoid IV reuse.
    
- Backward compatible with older hardware (via firmware updates).
    

#### 🔻 Weaknesses:

- TKIP is vulnerable to MIC (Message Integrity Check) attacks.
    
- Slower and less secure than newer protocols.
    
- **Deprecated** but still found in legacy systems.
    

---

### 3. **WPA2 (Wi-Fi Protected Access II)**

- **Introduced**: 2004
    
- **Encryption**: AES-CCMP (Advanced Encryption Standard - Counter Mode with Cipher Block Chaining Message Authentication Code Protocol)
    

#### 🔹 Features:

- Strong security with AES encryption.
    
- Mandatory for Wi-Fi certified devices after 2006.
    
- Includes **WPA2-Personal** (uses a pre-shared key) and **WPA2-Enterprise** (uses 802.1X authentication server).
    

#### 🔻 Weaknesses:

- Vulnerable to brute-force attacks if weak passwords are used.
    
- **KRACK Attack** (Key Reinstallation Attack) exploited WPA2's handshake vulnerabilities in 2017.
    
- Still widely used, but gradually being replaced by WPA3.
    

---

### 4. **WPA3 (Wi-Fi Protected Access III)**

- **Introduced**: 2018
    
- **Encryption**: SAE (Simultaneous Authentication of Equals), AES-GCMP
    

#### 🔹 Features:

- **Stronger password protection** even with weak passwords (resists offline dictionary attacks).
    
- **Forward secrecy** – previous session keys cannot be compromised even if long-term keys are.
    
- **Enhanced protection** for open networks via **Opportunistic Wireless Encryption (OWE)**.
    
- **Mandatory 192-bit encryption** for WPA3-Enterprise.
    

#### 🔻 Weaknesses:

- Requires new hardware.
    
- Still being adopted across devices and routers.
    

---

## Summary Comparison Table

|**Protocol**|**Introduced**|**Encryption**|**Security Level**|**Status**|
|---|---|---|---|---|
|**WEP**|1997|RC4|Low|Deprecated|
|**WPA**|2003|TKIP|Moderate|Deprecated|
|**WPA2**|2004|AES-CCMP|High|Widely used|
|**WPA3**|2018|AES-GCMP, SAE|Very High|Recommended (modern standard)|

---

## Best Practices for Wi-Fi Security

1. **Use WPA3** whenever possible.
    
2. Use strong, complex **passwords or passphrases**.
    
3. Regularly **update firmware** on routers and access points.
    
4. **Disable WPS (Wi-Fi Protected Setup)** as it can be exploited.
    
5. Use **enterprise mode** (802.1X) for business networks.
    
6. Use **guest networks** for visitors to isolate access.
    
7. Enable **MAC filtering** and network segmentation as additional layers.
    

---

Let me know if you'd like diagrams for WPA/WPA2 handshakes or a PDF version for easier studying!