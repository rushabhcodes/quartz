---
created: 2025-05-15T13:52
updated: 2025-05-15T13:57
---
To encrypt a message using the **Playfair cipher** with the key `"DOCUMENT"` and plaintext `"ALL THE BEST"`, we’ll follow these steps:

---

### **Step 1: Create the 5x5 Playfair matrix**

**Key**: `"DOCUMENT"` (remove duplicates, ignore case)  
Alphabet: A–Z (combine **I** and **J** as one letter)

**Unique letters in "DOCUMENT"**:

```
D O C U M E N T
=> D O C U M E N T
```

Now, fill the rest of the matrix with the remaining letters (excluding already used ones and combining I/J):

**Remaining letters**: A B F G H I/J K L P Q R S V W X Y Z

**Final 5x5 matrix**:

| D   | O   | C   | U   | M   |
| --- | --- | --- | --- | --- |
| E   | N   | T   | A   | B   |
| F   | G   | H   | I/J | K   |
| L   | P   | Q   | R   | S   |
| V   | W   | X   | Y   | Z   |

### **Step 2: Prepare the plaintext message**

**Message**: `ALL THE BEST`

1. Remove spaces: `ALLTHEBEST`
    
2. Break into digraphs (pairs). If same letters in a digraph, insert X between them. Pad the last with X if needed:
    

```
AL  LT  HE  BE  ST
```

(Notice that `LL` would normally be split as `LX LX`, but here it's split as `LT` — so we proceed as is.)

---

### **Step 3: Apply Playfair rules**

**Rules**:

1. Same row → replace each letter with the letter to its **right** (wrap around)
    
2. Same column → replace each letter with the letter **below** (wrap around)
    
3. Rectangle → replace each letter with the letter in its **row but in the column of the other letter**
    

---

Let’s encrypt each digraph using the matrix:

#### 1. **A L**
- A: row 2, col 3
- L: row 4, col 0 → Rectangle case  
    → Encrypted: **E P**
#### 2. **L T**
- L: row 4, col 0
- T: row 2, col 2 → Rectangle  
    → Encrypted: **Q F**
#### 3. **H E**
- H: row 3, col 2
- E: row 2, col 0 → Rectangle  
    → Encrypted: **F N**
#### 4. **B E**
- B: row 2, col 4
- E: row 2, col 0 → Same row  
    → Encrypted: **F N**
#### 5. **S T**
- S: row 4, col 4
- T: row 2, col 2 → Rectangle  
    → Encrypted: **Q H**
    
---

### **Final Ciphertext**:

```
E P Q F F N F N Q H
→ **EPQFFNFNQH**
```

---