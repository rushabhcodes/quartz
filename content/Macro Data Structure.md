## 1. **Macro Definition Table (MDT)**

- **Purpose**: Stores the **body** of all macro definitions (i.e., instructions between `MACRO` and `MEND`).
    
- **Each line** of a macro definition is stored in sequence.
    

#### Example:

```asm
MACRO
INCR &ARG
   ADD AREG, &ARG
MEND
```

#### MDT:

|Index|Instruction|
|---|---|
|0|INCR &ARG|
|1|ADD AREG, &ARG|
|2|MEND|

---

## 2. **Macro Name Table (MNT)**

- **Purpose**: Holds the names of defined macros and their **starting index in MDT**.
    
- Used to quickly locate macro bodies during expansion.
    

#### MNT:

|Index|Macro Name|MDT Index|
|---|---|---|
|0|INCR|0|

---

## 3. **Macro Definition Table Counter (MDTC)**

- **Purpose**: Points to the **next available entry** in the MDT.
    
- Updated as macro lines are inserted.
    
- Starts from 0 and increments with every new line added.
    

#### Example:

- Before macro insertion: `MDTC = 0`
    
- After above macro: `MDTC = 3`
    

---

## 4. **Macro Name Table Counter (MNTC)**

- **Purpose**: Points to the **next available entry** in the MNT.
    
- Incremented each time a new macro is defined.
    

#### Example:

- After defining `INCR`, `MNTC = 1`
    

---

## 5. **Argument List Array (ALA)**

- **Purpose**: Maintains a list of **formal parameters** during macro definition and replaces them with **actual parameters** during macro expansion.
    
- Ensures proper parameter substitution.
    

#### Macro Call:

```asm
INCR NUM1
```

#### ALA During Expansion:

|Index|Formal Arg|Actual Arg|
|---|---|---|
|0|&ARG|NUM1|

- During expansion, `&ARG` is replaced by `NUM1` in the instructions.
    

---

## Summary Table:

|**Structure**|**Purpose**|
|---|---|
|MDT|Stores macro body (excluding MACRO keyword)|
|MNT|Stores macro names and corresponding MDT index|
|MDTC|Tracks next available index in MDT|
|MNTC|Tracks next available index in MNT|
|ALA|Manages argument substitution|
