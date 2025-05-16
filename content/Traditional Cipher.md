Traditional ciphers are cryptographic techniques used historically to secure messages. They rely on simple mathematical or letter-based manipulations rather than complex algorithms like modern encryption. These ciphers are generally categorized into:

1. **Substitution ciphers** – replace elements of the plaintext with ciphertext (e.g., letters replaced with other letters).

2. **Transposition ciphers** – rearrange the order of characters in the plaintext without changing the actual characters.

---

### 1. **Substitution Cipher Example: Caesar Cipher**

**Definition**:  
In a Caesar cipher, each letter in the plaintext is shifted a fixed number of places down the alphabet.

**Example (Shift = 3)**:

- Plaintext: `HELLO`

- Ciphertext: `KHOOR`

- H → K

- E → H

- L → O

- L → O

- O → R


**Merits**:

- Simple to implement and understand.

- Requires minimal computational resources.

**Demerits**:

- Easily broken using frequency analysis or brute-force (only 25 possible shifts).

- Not secure for modern communication.


---

### 2. **Transposition Cipher Example: Rail Fence Cipher**

**Definition**:  
The letters of the plaintext are written in a zig-zag pattern (rails) and then read row-wise to form the ciphertext.

**Example (Depth = 3)**:

- Plaintext: `WEAREDISCOVERED`

- Zigzag writing:

```
W . . . R . . . D . . .
. E . E . D . C . V . R
. . A . . . I . . . E .
```

- Ciphertext: `WRDEEDCVREAIE`


**Merits**:

- Preserves letter frequency, making frequency analysis harder.

- Adds confusion by changing the order of letters.


**Demerits**:

- Still vulnerable to pattern detection.

- Requires knowledge of the transposition key (e.g., number of rails).
