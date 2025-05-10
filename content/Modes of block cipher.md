Block ciphers (like AES, DES) encrypt data in fixed-size blocks (e.g., 128 bits for AES). But real-world data is usually longer or shorter than the block size, so **modes of operation** define **how to repeatedly apply a block cipher** to encrypt/decrypt data of arbitrary length securely.

Here are the **most common block cipher modes**:

---

## 🔒 1. **ECB (Electronic Codebook Mode)**

### 📌 How it works:

Each block is encrypted **independently** using the same key.

```
C₁ = E(K, P₁)
C₂ = E(K, P₂)
...
```

### ✅ Pros:

- Simple and fast.
- Allows parallel encryption.

### ❌ Cons:

- **Patterns leak** (identical plaintext blocks produce identical ciphertexts).
- **Not semantically secure.**

### 📘 Example:

Encrypting a BMP image with ECB will reveal the original image structure.

---

## 🔄 2. **CBC (Cipher Block Chaining Mode)**

### 📌 How it works:

Each plaintext block is XORed with the previous ciphertext block before encryption. First block uses an **IV (Initialization Vector)**.

```
C₁ = E(K, P₁ ⊕ IV)
C₂ = E(K, P₂ ⊕ C₁)
...
```

### ✅ Pros:

- Hides patterns.
- Widely used and secure if IV is random.

### ❌ Cons:

- Slower due to chaining (no parallel encryption).
- Errors propagate (one corrupted block affects the next).

---

## 🔁 3. **CFB (Cipher Feedback Mode)**

### 📌 How it works:

Turns a block cipher into a **stream cipher**. Previous ciphertext block is encrypted and XORed with plaintext.

```
C₁ = P₁ ⊕ E(K, IV)
C₂ = P₂ ⊕ E(K, C₁)
...
```

### ✅ Pros:

- Can work with partial (non-block-size) data.
- No padding needed.

### ❌ Cons:

- Sequential processing (no parallelism).
- Bit errors propagate.

---

## 🔄 4. **OFB (Output Feedback Mode)**

### 📌 How it works:

Similar to CFB, but instead of using ciphertext for the next round, it uses the encrypted output.

```
O₁ = E(K, IV)
C₁ = P₁ ⊕ O₁  
O₂ = E(K, O₁)
C₂ = P₂ ⊕ O₂  
...
```

### ✅ Pros:

- Errors do **not propagate**.
- Preprocessing possible (parallelizable output stream).

### ❌ Cons:

- Sensitive to IV reuse (compromises security).

---

## 🧮 5. **CTR (Counter Mode)**

### 📌 How it works:

Encrypts a **counter** (nonce + counter) and XORs it with plaintext. Acts like a stream cipher.

```
C₁ = P₁ ⊕ E(K, CTR₁)
C₂ = P₂ ⊕ E(K, CTR₂)
...
```

### ✅ Pros:

- Fully parallelizable.
- Fast and efficient.
- Random access possible.

### ❌ Cons:

- Must **never reuse** nonce+counter with the same key.

---

## 🔁 Comparison Table:

|Mode|Parallel Encrypt|Pattern Leak|Needs IV|Stream Mode|Error Propagation|
|---|---|---|---|---|---|
|ECB|✅|❌ Yes|❌ No|❌ No|❌ No|
|CBC|❌|✅ No|✅ Yes|❌ No|Affects next block|
|CFB|❌|✅ No|✅ Yes|✅ Yes|Affects next block|
|OFB|✅|✅ No|✅ Yes|✅ Yes|No propagation|
|CTR|✅|✅ No|✅ Yes|✅ Yes|No propagation|
