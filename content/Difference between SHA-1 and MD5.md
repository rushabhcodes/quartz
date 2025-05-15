## 1. **Basic Details**

|Feature|**MD5**|**SHA-1**|
|---|---|---|
|Full Form|Message Digest 5|Secure Hash Algorithm 1|
|Developed By|Ronald Rivest (1991)|NSA (1995), published by NIST|
|Output Size|128 bits (32 hex chars)|160 bits (40 hex chars)|
|Block Size|512 bits|512 bits|
|Speed|Faster|Slightly slower|

---

## 2. **Security**

|Aspect|**MD5**|**SHA-1**|
|---|---|---|
|Collision Resistance|Weak (collisions found easily)|Weak (collisions also found)|
|Preimage Resistance|Poor|Better than MD5 but still broken|
|Cryptanalysis|Broken (many published attacks)|Broken (Google's SHAttered attack)|

### Real-World Attacks:

- **MD5:** Flame malware, rogue certificates, password hashes cracked.

- **SHA-1:** [SHAttered (2017)](https://shattered.io) - First practical collision found using two PDFs.


---

## 3. Use Cases (Current Status)

| Use Case           | MD5                       | SHA-1                     |
| ------------------ | ------------------------- | ------------------------- |
| File Checksums     | ✅ Still used (non-secure) | ✅ Still used (non-secure) |
| Digital Signatures | ❌ Unsafe                  | ❌ Unsafe                  |
| Certificates       | ❌ Deprecated              | ❌ Deprecated              |
| Password Hashing   | ❌ Not recommended         | ❌ Not recommended         |

> [!note] **Preferred secure alternatives:**

- Use **SHA-256** or **SHA-3** for cryptographic use.

- Use **bcrypt**, **scrypt**, or **Argon2** for password hashing.


---

## Example Hashes:

Plaintext: `hello`

- **MD5:** `5d41402abc4b2a76b9719d911017c592`

- **SHA-1:** `aaf4c61ddcc5e8a2dabede0f3b482cd9aea9434d`


---

## Summary

|Feature|MD5|SHA-1|
|---|---|---|
|Speed|Faster|Slower|
|Output Size|128-bit|160-bit|
|Security|Very weak (broken)|Weak (also broken)|
|Status|Deprecated for security use|Deprecated for security use|
