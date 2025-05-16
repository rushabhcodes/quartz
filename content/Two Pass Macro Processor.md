### Pass 1 – Macro Definition Processing

**Purpose:**  
The primary purpose of Pass 1 is to process all macro definitions in the source program and store them for use during Pass 2.

**Input:**  
The input to Pass 1 is the source program containing macro definitions and other assembly instructions. Macros are defined using the pseudo-operations `MACRO` and `MEND`.

**Working:**

1. The assembler reads each line of the source program.
    
2. If a line contains a `MACRO` pseudo-op, it indicates the start of a macro definition.
    
3. The next line, referred to as the macro prototype line, contains the macro name and its parameters.
    
4. The macro name and a pointer to the corresponding macro definition in the Macro Definition Table (MDT) are entered into the Macro Name Table (MNT).
    
5. Each line from the macro prototype to the `MEND` pseudo-op is stored sequentially in the MDT.
    
6. This process continues for all macro definitions.
    
7. When the assembler encounters the `END` pseudo-op, it indicates that all macro definitions have been processed, and control is transferred to Pass 2 for macro expansion.
    

**Data Structures Used:**

1. **Macro Name Table (MNT):** Stores the names of macros along with pointers to their definitions in the MDT.
    
2. **Macro Definition Table (MDT):** Stores the actual body of each macro definition.
    
3. **Argument List Array (ALA):** Temporarily stores formal and actual parameters during macro expansion (used more in Pass 2 but may be partially initialized in Pass 1).
    

**Output of Pass 1:**

- A completed MNT and MDT.
    
- The intermediate form of the source code is prepared for Pass 2.
    

![[Pass 1 Two Pass Macro.excalidraw.svg]]

### Pass 2 – Macro Calls and Expansion

**Purpose:**  
The purpose of Pass 2 is to expand all macro calls using the macro definitions collected during Pass 1, and to generate the final source program that can be passed to the assembler.

**Input:**

- Intermediate source code (with macro definitions)
    
- Macro Name Table (MNT)
    
- Macro Definition Table (MDT)
    

**Working:**

1. The assembler reads each line of the intermediate source code.
    
2. If the operation mnemonic of a line matches an entry in the Macro Name Table (MNT), it is recognized as a macro call.
    
3. The Macro Definition Table Pointer (MDTP) is set to the location in the MDT where the macro definition starts. This location is obtained from the MDT index in the MNT.
    
4. An Argument List Array (ALA) is prepared. This array maps dummy arguments (formal parameters) to actual arguments from the macro call. The first argument (if present) is the label and is given index zero.
    
5. For each argument in the call:
    
    - If an argument is missing, it is considered blank.
        
    - Extra arguments are ignored.
        
    - For positional arguments, the mapping is straightforward based on order.
        
    - For keyword arguments (references by name), the dummy argument is located in the macro prototype line in the MDT to determine its index.
        
6. The macro body is then read from the MDT line by line:
    
    - Dummy arguments are replaced by actual arguments from the ALA.
        
7. This process continues until a `MEND` pseudo-op is encountered, which marks the end of the macro expansion.
    
8. The expanded macro is inserted into the output stream.
    
9. The assembler continues processing the rest of the source lines.
    
10. When the `END` pseudo-op is encountered, Pass 2 is complete, and the expanded source code is passed to the assembler.
    

**Data Structures Used:**

1. **Macro Name Table (MNT):** Used to identify macro calls and provide pointers to the definitions in MDT.
    
2. **Macro Definition Table (MDT):** Stores the macro definitions to be expanded.
    
3. **Argument List Array (ALA):** Used to map dummy parameters to actual arguments during macro expansion.
    

**Output of Pass 2:**

- The fully expanded source program, ready for standard assembly processing.


![[Pass 2 Two Pass Macro.excalidraw.svg]]