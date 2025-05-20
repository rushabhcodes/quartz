A forward reference occurs when a label is used as an operand, for example as a branch target, earlier in the code than the definition of the label. The assembler cannot know the address of the forward reference label until it reads the definition of the label.

Example
```asm
JMP END     ; forward reference to END
...
END: NOP    ; definition of END appears later
```

In this case, the assembler encounters `END` before it knows its actual memory address.

## How Assemblers Handle Forward Reference

### 1. **Using a Two-Pass Assembler (Most Common Solution)**

#### **Pass 1:**

- Scans the code and **builds the symbol table**.

- Keeps track of **all labels** and their addresses.
   
- Generates **intermediate code** for every instruction.
  
#### **Pass 2:**

- Replaces all symbols (even forward-referenced ones) using the **symbol table** built in Pass 1.

- Generates the **final machine code**.
   

> This method **completely resolves forward references** because all label addresses are known by Pass 2.

---

### 2. **Back-patching in Single-Pass Assembler**

Since forward-referenced labels are not defined yet, a **back-patching** technique is used:
#### Technique:

- Leave a placeholder (blank) in the operand field for unresolved symbols.

- Maintain a **Table of Incomplete Instructions (TII)** that stores:
    - Instruction address
    - Symbol name

- When the label is finally defined:    
    - Update the **symbol table**
    - Use the **TII** to "patch" all instructions that used that symbol.
#### Table of Incomplete Instructions (TII) Format:

| **Instruction Address** | **Symbol** |
| ----------------------- | ---------- |
| 204                     | END        |
| 218                     | LOOP       |
### Summary

| **Approach**                  | **Used in**                       | **How it Handles Forward Reference**                   |
| ----------------------------- | --------------------------------- | ------------------------------------------------------ |
| Two-Pass Assembler            | Most compilers                    | Pass 1 builds symbol table, Pass 2 resolves references |
| Single-Pass with Backpatching | Resource-constrained environments | Leaves placeholders, fixes later using TII             |
