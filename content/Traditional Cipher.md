---
created: 2025-05-12T15:44
updated: 2025-05-14T22:50
---
Traditional ciphers are cryptographic techniques used historically to secure messages. They rely on simple mathematical or letter-based manipulations rather than complex algorithms like modern encryption. These ciphers are generally categorized into:

1. **Substitution ciphers** – replace elements of the plaintext with ciphertext (e.g., letters replaced with other letters).
	- **Caesar Cipher**: Shifts each letter a fixed number of places (e.g., A → D for a shift of 3).
	- **Monoalphabetic Cipher**: Uses a fixed substitution alphabet (e.g., A → Q, B → W, C → E, etc.).

2. **Transposition ciphers** – rearrange the order of characters in the plain-text without changing the actual characters.
	 - **Rail Fence Cipher**: Writes plaintext in a zigzag pattern across multiple lines.
	- **Columnar Transposition**: Writes plaintext in rows and reads off in a different column order based on a key.

3. **Product Cipher** - Combines substitution and transposition for better security.
	- **Playfair Cipher**: Encrypts digraphs (pairs of letters) using a 5x5 matrix.
	- **Hill Cipher**: Uses linear algebra (matrices) to encrypt groups of letters.