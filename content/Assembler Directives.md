## **What are Assembler Directives?**

Assembler directives (also called **pseudo-operations**) are **instructions for the assembler**, not the CPU.  
They **do not generate machine code**, but help in organizing and managing the assembly program during translation.

---

##  Common Assembler Directives (with Examples)

---

### 🔹 1. `START`

- **Purpose**: Specifies the starting address of the program.

- **Effect**: Initializes the **Location Counter (LC)**.

- **Syntax**: `START <address>`


#### 🧾 Example:

```asm
START 100
```

➡ Tells the assembler to begin translating the code at memory address `100`.

---

### 🔹 2. `END`

- **Purpose**: Marks the end of the program.

- **Effect**: Triggers processing of remaining **literals** and stops assembly.

- **Syntax**: `END`


#### 🧾 Example:

```asm
END
```

---

### 🔹 3. `ORIGIN`

- **Purpose**: Changes the value of the **Location Counter (LC)**.

- **Syntax**: `ORIGIN <address>`


#### 🧾 Example:

```asm
ORIGIN 200
```

➡ The next instruction will be assembled at address 200.

---

### 🔹 4. `EQU` (Equate)

- **Purpose**: Assigns a constant value to a symbol.

- **Effect**: Symbol is defined with a **fixed address or value**.

- **Syntax**: `<SYMBOL> EQU <value>`


#### 🧾 Example:

```asm
VAL EQU 500
```

➡ Whenever `VAL` is used, it's replaced by `500`. **LC is not affected.**

---

### 🔹 5. `LTORG` (Literal Pool Origin)

- **Purpose**: Tells the assembler to assign addresses to **literals** found so far.

- **Effect**: Allocates memory for literals and updates the **Literal Table (LITTAB)**.

- **Syntax**: `LTORG`


#### 🧾 Example:

```asm
MOVER AREG, =‘5’
LTORG
```

➡ Allocates memory for literal `=‘5’` at the current LC value.

---

### 🔹 6. `DC` (Define Constant)

- **Purpose**: Allocates memory and assigns a constant value.

- **Syntax**: `<SYMBOL> DC <value>`


#### 🧾 Example:

```asm
VALUE DC '10'
```

➡ Assigns 10 to the label `VALUE`.

---

### 🔹 7. `DS` (Define Storage)

- **Purpose**: Reserves memory locations.

- **Syntax**: `<SYMBOL> DS <size>`


#### 🧾 Example:

```asm
BUFFER DS 5
```

➡ Reserves 5 memory locations for `BUFFER`.

---

## Summary Table

|**Directive**|**Meaning**|**Example**|**Effect**|
|---|---|---|---|
|`START`|Start of program|`START 100`|Sets LC to 100|
|`END`|End of program|`END`|Triggers literal allocation & stops|
|`ORIGIN`|Changes LC|`ORIGIN 300`|Sets LC to 300|
|`EQU`|Assign value to symbol|`MAX EQU 500`|Defines symbol with constant value|
|`LTORG`|Allocate literal pool|`LTORG`|Assigns address to collected literals|
|`DC`|Define constant|`N DC '1'`|Allocates and stores value|
|`DS`|Reserve storage|`X DS 2`|Allocates 2 memory locations|
