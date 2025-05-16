---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---
Intermediate Code (IC) is an abstract representation of the source program generated after syntax and semantic analysis. It is independent of both the source and target machine, making the compilation process more flexible and portable.

---

### 1. **Syntax Tree**

- A **hierarchical tree structure** where:
    
    - Internal nodes represent **operators**.
        
    - Leaf nodes represent **operands (variables/constants)**.
        
- More concise than a parse tree.    

**Example (for expression `a + b * c`):**

```
      +
     / \
    a   *
       / \
      b   c
```

---

### 2. **Postfix Notation (Reverse Polish Notation)**

- A **linearized form** of the syntax tree.
    
- Operators follow their operands.
    
- No parentheses are needed.
    

**Infix**: `(a - b) * (c + d)`  
**Postfix**: `a b - c d + *`

---

### 3. **Three Address Code (TAC)**

- Each instruction has **at most three operands**.
    
- Simplifies complex expressions using **temporary variables**.
    

**Example for `a + b * c + d`:**

```
t1 = b * c  
t2 = a + t1  
t3 = t2 + d
```
