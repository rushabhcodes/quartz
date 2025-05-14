**Three Address Code (TAC)** is an intermediate code representation used in compilers during the translation of high-level language into machine code. It breaks complex expressions into simple statements that involve at most three operands.

---

### 1. **Structure**

Each instruction typically has the form:

```
x = y op z
```

Where:

- `x` = result (target)
    
- `y`, `z` = operands
    
- `op` = operator (arithmetic, logical, relational, etc.)
    

---

### 2. **Features**

- Simplifies code generation and optimization.
    
- Uses temporary variables to hold intermediate results.
    
- Makes control flow (like `if`, `goto`) and expressions easy to represent.
    

---

### 3. **Example**

For the expression:

```c
a + b * c + d
```

The TAC would be:

```asm
t1 = b * c  
t2 = a + t1  
t3 = t2 + d
```

---

### 4. **Forms of TAC Representation:**

#### a. **Quadruples**
It is structure with consist of 4 fields namely op, arg1, arg2 and result.

Op denotes the operator and arg1 and arg2 denotes the two operands and result is used to store the result of the expression.

|Index|Op|Arg1|Arg2|Result|
|---|---|---|---|---|
|1|*|b|c|t1|
|2|+|a|t1|t2|
|3|+|t2|d|t3|
Advantages
- Easy to rearrange code for global optimization.
- One can quickly access value of temporary variables using symbol table.
Disadvantages
- Contain lot of temporaries.
- Temporary variable creation increases time and space complexity.
#### b. **Triples**
This representation doesn’t make use of extra temporary variable to represent a single operation instead when a reference to another triple’s value is needed, a pointer to that triple is used.

So, it consist of only three fields namely op, arg1 and arg2.

|Index|Op|Arg1|Arg2|
|---|---|---|---|
|1|*|b|c|
|2|+|a|(1)|
|3|+|(2)|d|

---

### 5. **Applications**

- Intermediate step in code optimization.

- Used in target code generation phase of the compiler.


---

### **In Summary**

Three Address Code is a simple, flexible, and powerful way to represent high-level expressions and control structures, making it easier for compilers to optimize and generate machine-level code.