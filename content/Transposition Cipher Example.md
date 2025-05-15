---
created: 2025-05-14T22:50
updated: 2025-05-14T22:51
---
### **1. Rail Fence Cipher**

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
