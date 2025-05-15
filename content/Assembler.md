---
created: 2025-05-14T21:51
updated: 2025-05-14T21:51
---
An **assembler** is a **system program** that **translates an assembly language program** into **machine code (object code)** that can be executed by the CPU.

## Key Functions of an Assembler

1. Converts **opcode mnemonics** (e.g., `MOV`, `ADD`) into machine instructions.
2. Assigns memory addresses using a **Location Counter (LC)**.
3. Handles **symbols** (labels), **constants**, and **literals**.
4. Supports **forward referencing** (resolves references made before symbol definitions).   
5. Generates **intermediate code** and final **machine code**.

## Data Structures Used in Assembler

### 1. **POT – Pseudo Opcode Table**

#### Purpose

The **Pseudo Opcode Table (POT)** stores **assembler directives**. These are not real machine instructions but guide the assembler on how to manage memory or control flow.

#### Contents

- Directive name
- Class (`AD` = Assembler Directive)
- Code (identifier for processing)

#### Example

|**Directive**|**Class**|**Opcode/ID**|
|---|---|---|
|START|AD|01|
|END|AD|02|
|ORIGIN|AD|03|
|EQU|AD|04|
|LTORG|AD|05|

#### Usage

`START 100` sets the **Location Counter (LC)** to 100. The assembler finds `START` in the POT to perform this operation.

---

### 2. **MOT – Mnemonic Opcode Table**

#### Purpose

The **Mnemonic Opcode Table (MOT)** contains all **machine instructions** (imperative statements) and their corresponding **opcodes**, formats, and operand types.

#### Contents

- Mnemonic
- Instruction Class (`IS` = Imperative Statement)
- Opcode
- Operand count/type

#### Example

|**Mnemonic**|**Class**|**Opcode**|**Operands**|
|---|---|---|---|
|MOVER|IS|04|2|
|ADD|IS|01|2|
|SUB|IS|02|2|
|STOP|IS|00|0|

#### Usage

When the assembler sees `MOVER AREG, VALUE`, it looks up `MOVER` in MOT to get opcode `04`.

---

### 3. **ST – Symbol Table**

#### Purpose

The **Symbol Table (ST)** stores all **user-defined labels or variables** and their corresponding memory addresses.

#### Contents

- Symbol name
- Address (assigned using LC)
- Length (optional)

#### Example

|**Symbol**|**Address**|**Length**|
|---|---|---|
|LOOP|200|1|
|VALUE|202|1|
|ENDLABEL|210|1|

#### Usage

When the assembler encounters `JMP LOOP`, it looks up `LOOP` in ST to retrieve its address (`200`).

---

### 4. **LT – Literal Table**

#### Purpose

The **Literal Table (LT)** keeps track of **constants/literals** used in the program and their resolved memory addresses.

#### Contents

- Literal (e.g., `='5'`)
- Address (assigned after `LTORG` or `END`)

#### Example

|**Literal**|**Address**|
|---|---|
|`='5'`|211|
|`='1'`|212|

#### Usage

Instruction like `MOVER AREG, =‘5’` adds `='5'` to LT during Pass 1, and address `211` is assigned during `LTORG`.

---

### 5. **BT – Base Table**

#### Purpose

The **Base Table (BT)** is used in **base register addressing** schemes to manage

- Which registers are defined as **base**
- What **addresses** are currently loaded in those registers

#### Contents

- Register name
- Base address

#### Example

|**Register**|**Address**|
|---|---|
|BREG|100|
|DREG|200|

#### Usage

In indexed addressing, the assembler uses BT to calculate effective address using base + displacement.

---

## 🧪 **Example Assembly Code**

```asm
START 100
LOOP   MOVER AREG, =‘5’
       ADD   AREG, VALUE
VALUE  DC    ‘1’
       END
```

### 🧾 Tables Populated

- **POT** → `START`, `END`
    
- **MOT** → `MOVER`, `ADD`, `DC`
    
- **ST** → `LOOP = 100`, `VALUE = 102`
    
- **LT** → `='5' = 103` (after `END`)
    
- **BT** → If base registers are used (optional)
    
### Summary Table

|**Table**|**Full Name**|**Purpose**|
|---|---|---|
|**MOT**|Mnemonic Opcode Table|Maps instructions like `MOVER` or `ADD` to machine opcodes and formats|
|**POT**|Pseudo Opcode Table|Holds assembler directives like `START`, `END`, `EQU`, `LTORG`|
|**SYMTAB (ST)**|Symbol Table|Stores labels and their memory addresses|
|**LITTAB (LT)**|Literal Table|Stores literal constants (e.g., `='5'`) and their resolved addresses|
|**BT**|Base Table|Tracks registers used for base-addressing and their assigned addresses|
