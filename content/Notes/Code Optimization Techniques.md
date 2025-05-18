---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---
## **Code Optimization Techniques**

**Code optimization** is a phase in compiler design aimed at **improving the intermediate code** to make the final executable **more efficient**, without changing the program's output or logic.

Optimization can target:
- **Execution speed**
- **Memory usage**
- **Power consumption** (in embedded systems)

There are two types:
- **Machine-independent optimization** (applied on IR)
- **Machine-dependent optimization** (applied during or after code generation)

---

## 🔹 **1. Constant Folding**

- **Description**: Compile-time evaluation of constant expressions.
    
- **Benefit**: Saves runtime computation.
    

**Example:**

```c
int x = 3 * 5;
```

**Optimized to:**

```c
int x = 15;
```

---

## 🔹 **2. Constant Propagation**

- **Description**: Replaces variables with known constant values.
    
- **Benefit**: Simplifies expressions and exposes more optimization opportunities.
    

**Example:**

```c
int a = 10;
int b = a + 5;
```

**Optimized to:**

```c
int b = 10 + 5;
```

---

## 🔹 **3. Common Sub-expression Elimination (CSE)**

- **Description**: Eliminates duplicate expressions already computed.
    
- **Benefit**: Reduces redundant calculations.
    

**Example:**

```c
t1 = a + b;
t2 = a + b;
```

**Optimized to:**

```c
t1 = a + b;
t2 = t1;
```

---

## 🔹 **4. Dead Code Elimination**

- **Description**: Removes code that does not affect program output.
    
- **Benefit**: Reduces program size and increases speed.
    

**Example:**

```c
int x = 10;
x = 20;   // x = 10 is dead code
```

**Optimized to:**

```c
int x = 20;
```

---

## 🔹 **5. Strength Reduction**

- **Description**: Replaces expensive operations with cheaper equivalents.
    
- **Benefit**: Improves execution time.
    

**Example:**

```c
x = a * 2;      // multiplication
```

**Optimized to:**

```c
x = a + a;      // faster addition
```

---

## 🔹 **6. Loop Invariant Code Motion**

- **Description**: Moves code that computes the same result in every iteration **outside the loop**.
    
- **Benefit**: Reduces redundant computations inside loops.
    

**Example:**

```c
for (int i = 0; i < n; i++) {
    x = a * b;
    arr[i] = x + i;
}
```

**Optimized to:**

```c
x = a * b;
for (int i = 0; i < n; i++) {
    arr[i] = x + i;
}
```

---

## 🔹 **7. Copy Propagation**

- **Description**: Replaces occurrences of variables that are copies of others.
    
- **Benefit**: Enables further optimizations like dead code elimination.
    

**Example:**

```c
b = a;
c = b + 1;
```

**Optimized to:**

```c
c = a + 1;
```

---

## 🔹 **8. Peephole Optimization**

- **Description**: Looks at small sliding windows ("peepholes") of instructions to perform local optimizations.
    
- **Benefit**: Simple and effective for final-stage optimization.
    

**Example:**

```asm
MOV R1, R2
MOV R2, R1
```

**Optimized to:** _(No effect)_

```
// Removed (they cancel each other)
```

---

## Summary Table

|**Technique**|**Purpose**|**Key Benefit**|
|---|---|---|
|Constant Folding|Evaluate expressions at compile time|Faster execution|
|Constant Propagation|Replace vars with constants|Exposes more optimizations|
|Common Sub-expression Elim.|Avoid recomputation|Reduces redundant code|
|Dead Code Elimination|Remove unused code|Smaller, faster code|
|Strength Reduction|Use cheaper operations|Improves performance|
|Loop Invariant Code Motion|Move code out of loops|Reduces loop overhead|
|Copy Propagation|Replace variable copies|Simplifies expressions|
|Peephole Optimization|Small local improvements|Refines final output|
