**Transposition ciphers** rearrange the positions of characters in the plaintext to create ciphertext, rather than substituting characters with others (as substitution ciphers do). Transposition ciphers can be **keyed** or **keyless**.

---

## 🔐 1. Keyless Transposition Cipher

A **keyless transposition cipher** uses a fixed rule for rearranging the characters, without using a specific key.

### 🧠 Logic:

Usually, the plaintext is written in rows of a fixed length, then read off in columns (or vice versa).

### 📘 Example:

Let’s use 4-column transposition:

**Plaintext:** `HELLOTHISISSECRET`

**Step 1: Write in rows of 4:**

```
H E L L  
O T H I  
S I S S  
E C R E  
T
```

**Step 2: Pad last row (if needed):**

```
H E L L  
O T H I  
S I S S  
E C R E  
T X X X
```

**Step 3: Read column-wise:**

```
Column 1: H O S E T  
Column 2: E T I C X  
Column 3: L H S R X  
Column 4: L I S E X
```

**Ciphertext:** `HOSETETICLHSRXLISX`

---

## 🔑 2. Keyed Transposition Cipher (Columnar Transposition)

A **keyed transposition cipher** uses a keyword to determine the order in which columns are read.

### 🧠 Logic:

1. Write the plaintext in rows under columns labeled by the keyword.
    
2. Sort the columns alphabetically by the keyword.
    
3. Read off the columns in this new order.
    

### 📘 Example:

**Plaintext:** `DEFENDTHEEASTWALL`

**Keyword:** `ZEBRAS`

### Step 1: Number the keyword alphabetically:

```
Z E B R A S
6 3 1 5 0 4   (0-indexed alphabetical order)
```

### Step 2: Fill grid with plaintext:

```
Z  E  B  R  A  S
D  E  F  E  N  D
T  H  E  E  A  S
T  W  A  L  L  X
```

### Step 3: Read columns in order: 0,1,3,4,5,6 → A,B,E,S,R,Z

```
Column A (4): N A L  
Column B (2): F E A  
Column E (1): E H W  
Column S (5): D S X  
Column R (3): E E L  
Column Z (0): D T T
```

**Ciphertext:** `NALFEAEHWD SXEELDTT`

---

## Summary

|Type|Uses Key?|Pattern|Example|
|---|---|---|---|
|Keyless|❌|Fixed row/column|`HELLO → HOSETETIC...`|
|Keyed|✅|Keyword determines column order|`DEFEND → NALFEA...`|
