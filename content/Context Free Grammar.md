---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---
### 📘 **Definition:**

A **Context-Free Grammar (CFG)** is a formal grammar used to define the **syntactic structure** of programming languages. It is called _context-free_ because the rules (productions) can be applied **regardless of the surrounding symbols (context)**.

---

### 📐 **Components of CFG:**

A CFG is defined by a 4-tuple:  
**G = (V, Σ, P, S)** where:

|Symbol|Meaning|
|---|---|
|**V**|Finite set of **non-terminal symbols** (e.g., `S`, `stmt`, `expr`)|
|**Σ**|Finite set of **terminal symbols** (tokens or characters from input)|
|**P**|Finite set of **production rules** (e.g., `S → aSb`)|
|**S**|**Start symbol** (a special non-terminal from where derivation begins)|

---

### ✍️ **Example CFG:**

Let’s define a simple grammar for balanced parentheses:

```
V = {S}
Σ = {(, )}
P = {
     S → (S)
     S → SS
     S → ε
}
S = S
```

This grammar can generate strings like `()`, `(())`, `()()`, `(()())`, etc.

---

### 🔍 **Usage in Syntax Analysis:**

In the **second phase of a compiler**, called **Syntax Analysis (Parsing)**, the CFG is used to:

- Check **whether a given sequence of tokens** follows the grammatical rules of the programming language.
    
- Build a **parse tree** or **syntax tree** representing the hierarchical structure of the program.
    

---

### 🌲 **Parse Tree:**

A **parse tree** is a tree representation that shows how a string of terminals is derived using the grammar rules.

Example: For `(()())`, a parse tree can be constructed using CFG rules that show how each `(` and `)` is derived.

---

### 🧠 **Why CFG in Compilers?**

- Programming languages have **nested structures** (like if-else, loops, function calls), which CFG can naturally express.
    
- Helps in building parsers (like LL, LR parsers).
    
- Ensures **syntax correctness** before semantic analysis.
    

---

### ✅ **Advantages of CFG:**

- Can describe almost all programming language constructs.
    
- Can be parsed using efficient algorithms (LL, LR, LALR).
    
- Useful for developing automatic parsers.
    

---

### ❗ Limitations:

- Cannot express **context-sensitive constructs** like matching variable declarations and their uses (handled in semantic analysis).
    
- Cannot enforce rules like "a variable must be declared before use."
    

---

### 📝 Summary Table

|Feature|Description|
|---|---|
|Definition|A formal grammar defining syntax rules|
|Main Use|Syntax analysis in compilers|
|Structure|G = (V, Σ, P, S)|
|Produces|Parse tree / Syntax tree|
|Example|`S → (S)` `S → SS` `S → ε`|
|Parses|Programming language constructs like expressions|
