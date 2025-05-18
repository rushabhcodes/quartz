---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---
**DES (Data Encryption Standard)** is a symmetric-key block cipher developed by IBM and adopted by the U.S. government in the 1970s. It encrypts data in **64-bit blocks** using a **56-bit key**.

## Key Features

| Feature| Description|
| -------------- | ------------------------------------------------------ |
| **Type**   | Symmetric Key (same key for encryption and decryption) |
| **Block Size** | 64 bits|
| **Key Size**   | 56 bits (plus 8 parity bits, total 64 bits)|
| **Rounds** | 16 rounds of processing|
| **Structure**  | Feistel Network|
## High-Level DES Process

### 1. **Initial Permutation (IP)**

- A fixed initial permutation is applied to the 64-bit plaintext block.


### 2. **16 Rounds of Feistel Cipher**

- The block is divided into two halves: Left (L) and Right (R) — each 32 bits.

- Each round performs the following:

	- `L[i] = R[i-1]`
	
	- `R[i] = L[i-1] ⊕ f(R[i-1], K[i])`  
_(Here, `f()` is a round function and `K[i]` is the subkey for round i)_


### 3. **Function f (The Round Function)**

- Takes a 32-bit input and a 48-bit subkey.

- Steps inside `f()`:

	1. **Expansion (E-box):** Expands 32-bit input to 48 bits.
	
	2. **Key Mixing:** XOR with 48-bit subkey.
	
	3. **Substitution (S-boxes):** Divides into 8 blocks of 6 bits, each passed through an S-box to get 4 bits. Output: 32 bits.
	
	4. **Permutation (P-box):** Rearranges the 32 bits.


### 4. **Final Permutation (FP or IP⁻¹)**

- Inverse of the initial permutation is applied to the final output of the 16 rounds.