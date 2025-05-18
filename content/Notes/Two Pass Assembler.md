---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---
A **Two Pass Assembler** translates an **assembly language program** into machine code using **two passes** over the source code:

- **Pass 1**: Analyzes and collects data like labels, symbols, and literal addresses.
- **Pass 2**: Uses the collected data to generate actual machine instructions.

![[Pass 1 of 2 Pass Assembler.excalidraw.svg]]

## 🧾 Pass 1 of the Assembler

The purpose of **Pass 1** is to **assign memory locations to each instruction and data-defining pseudo-instruction**, thereby defining values for **symbols** that appear in the label fields of the source program.

Initially, the **Location Counter (LC)** is set to the starting address of the program (usually relative address 0). The assembler then reads a source statement.

### 🔍 Instruction Processing

- The **operation-code field** is examined to determine whether it is a **pseudo-op**.
    
- If it is **not a pseudo-op**, the **Machine Op-Code Table (MOT)** is searched to match the op-code.
    
- The matching MOT entry provides the **length** of the instruction (typically 2, 4, or 6 bytes).
    
- The **operand field** is scanned for **literals**. If a new literal is found, it is added to the **Literal Table (LT)** for later processing.
    
- The **label field** is then examined:
    
    - If a **symbol** is present, it is entered into the **Symbol Table (ST)** along with the current value of the location counter.
        
- The **location counter is incremented** by the instruction length.
    
- A **copy of the source line** is saved for use by **Pass 2**.
    

This process is repeated for each source statement.

---

### ⚙️ Handling Pseudo-Operations (Pseudo-Ops)

Pass 1 handles only those pseudo-ops that either:

- **Define symbols**, or
    
- **Affect the location counter**
    

#### ✅ `USING` and `DROP`

- These are simply **saved** for **Pass 2**.
    
- Pass 1 does not perform any processing beyond saving the cards.
    

#### ✅ `EQU`

- Pass 1 uses this to **define a symbol** in the label field.
    
- It evaluates the **expression in the operand field** to determine the symbol’s value.
    

#### ✅ `DS` and `DC`

- These pseudo-ops can:
    
    - **Define symbols**, and
        
    - **Affect the location counter**
        
- The operand field is examined to determine the **amount of storage required**.
    
- Due to **alignment requirements** (e.g., full words must start at addresses that are multiples of 4), the location counter may be adjusted before assigning the address.
    

---

### 🔚 End of Pass 1

When the `END` pseudo-op is encountered, **Pass 1 is terminated**.

Before transferring control to **Pass 2**, the assembler performs **housekeeping tasks**, such as:

- Assigning locations to **literals** collected during Pass 1.
    
    - This is similar to processing `DC` pseudo-ops.
        
- Reinitializing conditions and data structures required for **Pass 2**.



![[Pass 2 of 2 Pass Assembler.excalidraw.svg]]
## 🧾 Pass 2 of the Assembler: Code Generation

After **Pass 1** has defined all the **symbols**, **Pass 2** completes the assembly process by:

- Generating **machine code** for each instruction.
    
- Formatting the code for **loader compatibility**.
    
- Printing an **assembly listing** that includes both the source statement and the corresponding **hexadecimal machine code**.
    

---

### 🏁 Initialization

- The **Location Counter (LC)** is re-initialized, just like in Pass 1.
    
- Processing starts by reading each source statement saved during Pass 1.
    

---

### 🔍 Instruction Processing

1. **Identify Pseudo-ops:**
    
    - If the statement is a **pseudo-op**, it is handled separately (explained below).
        
    - If it is **not a pseudo-op**, the **Machine Op-Code Table (MOT)** is searched to:
        
        - Identify the instruction format (e.g., RR, RX),
            
        - Get the **binary op-code**, and
            
        - Determine the **length** of the instruction.
            
2. **Operand Processing:**
    
    - **RR-format (Register-to-Register):**
        
        - Both register fields are evaluated and inserted into their respective 4-bit fields.
            
    - **RX-format (Register and Storage):**
        
        - Register and index fields are evaluated similarly.
            
        - The **effective address (EA)** is calculated from the operand field.
            
        - The base and displacement fields are computed using the **Base Table (BT)**.
            
3. **Code Generation:**
    
    - The assembled instruction is formatted for the loader.
        
    - Several machine instructions may be grouped into a single output card.
        
    - A **listing line** is printed that includes:
        
        - The source statement,
            
        - Its assigned memory location,
            
        - And the generated machine code in hexadecimal.
            
    - The **Location Counter** is then incremented accordingly.
        

---

### ⚙️ Pseudo-op Processing

- **`EQU`:**
    
    - Requires minimal processing.
        
    - Symbol definition was already completed in Pass 1.
        
    - Simply printed in the assembly listing.
        
- **`USING` and `DROP`:**
    
    - Were ignored in Pass 1 but are important in Pass 2.
        
    - The **operand fields** are evaluated.
        
    - The corresponding **Base Table (BT)** entry is:
        
        - Marked as **available** if `USING`,
            
        - Marked as **unavailable** if `DROP`.
            
- **`DS` and `DC`:**
    
    - As in Pass 1, the location counter is updated based on required storage.
        
    - **`DC` (Define Constant)** also requires **actual code generation** in Pass 2:
        
        - May involve conversions (e.g., character → binary, float → machine format),
            
        - May include evaluations of address constants or symbolic values.
            

---

### 🧾 Handling Literals

- At the end of the source program (upon encountering the `END` pseudo-op):
    
    - **Remaining literals** in the **Literal Table (LT)** are processed.
        
    - Code is generated for each literal, similar to `DC`.
        

---

### ✅ Final Output

- All machine instructions are formatted for the loader.
    
- The complete **assembly listing** is printed.
    
- The program is now ready for **loading and execution**.
    