## **Phases of a Compiler**

A **compiler** is a complex software system that translates a **high-level programming language** (like C, Java) into **low-level machine code** that a computer can execute. This translation is done in **multiple systematic phases**, each performing a specific task to ensure the final code is **correct**, **optimized**, and **efficient**.

![[Phases of Compiler.excalidraw.svg]]

---

### **1. Lexical Analysis (Scanner Phase)**

- **Purpose**: The lexical analyzer (or scanner) is the first phase of the compiler. It reads the **raw source code** character by character and groups them into meaningful sequences called **tokens**.

- **Tokens** are atomic units like keywords (`if`, `while`), identifiers (`x`, `sum`), operators (`+`, `-`), literals (`10`, `'a'`), and punctuation (`;`, `{}`).

- It also removes **whitespace** and **comments**.

- **Example**:  
Source code: `int a = b + 10;`  
Tokens: `int`, `id(a)`, `=`, `id(b)`, `+`, `num(10)`, `;`

- **Output**: A stream of tokens passed to the next phase.

- **Data Structures Used**: Symbol Table (to store identifiers), Token stream.


---

### **2. Syntax Analysis (Parser Phase)**

- **Purpose**: The syntax analyzer (parser) receives the token stream from the lexical analyzer and verifies if the sequence of tokens **follows the rules** of the **context-free grammar** of the language.

- It builds a **parse tree** or **syntax tree**, representing the syntactic structure of the program.

- This phase also **detects syntax errors** such as missing semicolons, unmatched parentheses, or incorrect nesting.

- **Example**:  
Expression: `a + b * c`  
Parse Tree:

```
    *
   / \
  +   c
 / \
a   b
```

- **Output**: A parse tree or abstract syntax tree (AST).

- **Tools Used**: Parsers like LL, LR, YACC, Bison.


---

### **3. Semantic Analysis**

- **Purpose**: This phase checks for **semantic consistency** in the syntax tree. It ensures that:

- All variables are declared before use.

- Data types match (no type mismatch).

- Functions are called with the correct number/type of arguments.

- It uses **symbol tables** to track identifier declarations and scopes.

- It also **annotates** the syntax tree with semantic information.

- **Example**:

```c
int a = 5.5;  // Error: assigning float to int
```

- **Output**: Annotated Syntax Tree (with semantic information).

- **Data Structures Used**: Symbol Table (updated with types, scopes, etc.)


---

### **4. Intermediate Code Generation**

- **Purpose**: Converts the annotated syntax tree into an **intermediate representation (IR)** that is independent of machine architecture.

- This IR bridges the gap between high-level language and machine code and facilitates optimization and easy translation to various target machines.

- Common forms of IR include:

- **Three Address Code (TAC)**

- **Quadruples / Triples**

- **Control Flow Graph (CFG)**

- **Example** (for `a + b * c`):

```text
t1 = b * c
t2 = a + t1
```

- **Advantages**:

- Simplifies later phases.

- Helps apply machine-independent optimizations.

- **Output**: Intermediate code (e.g., TAC).


---

### **5. Code Optimization (Optional but Important)**

- **Purpose**: Refines the intermediate code to improve performance (speed, memory) **without changing the output** of the program.

- **Types of Optimizations**:

- **Local Optimization**: Within a basic block (e.g., constant folding)

- **Global Optimization**: Across procedures (e.g., loop invariant code motion)

- **Dead Code Elimination**: Removes statements that have no effect.

- **Example**:

```c
int x = 5;
x = 10;   // 'x = 5;' is dead code and can be eliminated
```

- **Output**: Optimized intermediate code.


---

### 6. Code Generation

- **Purpose**: Converts the optimized intermediate code into actual **target machine code** or **assembly code** that can be executed by the processor.

- This phase considers:

- **Instruction Selection**: Choosing the best machine instructions.

- **Register Allocation**: Assigning variables to CPU registers.

- **Instruction Scheduling**: Reordering for better CPU pipeline performance.

- **Example** (for `t3 = a + b` in TAC):

```asm
MOV R1, a
ADD R1, b
MOV c, R1
```

- **Output**: Target machine code or assembly instructions.

- **Challenges**:

- Target-specific constraints (ISA, registers, memory models).

- Efficient use of resources.


---

## **Conclusion**

The phases of a compiler up to code generation transform human-readable source code into an efficient and accurate low-level form. Each phase plays a crucial role in ensuring the correctness, performance, and portability of the final executable. By breaking down the compilation process, modern compilers become modular, manageable, and extensible.