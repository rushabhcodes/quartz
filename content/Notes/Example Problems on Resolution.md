---
created: 2025-05-19T01:55
updated: 2025-05-19T02:00
---
# Example 1

Consider the following statements: (asked twice)
a) All people who are graduating are happy
b) All happy people smile
c) Someone is graduating
Represent above statements in FOL, Convert each to CNF, Prove that “someone is
smiling” using resolution. Draw the resolution tree
## Problem Statements

**Given:**

1. All people who are graduating are happy
    
2. All happy people smile
    
3. Someone is graduating
    

**Goal:** Prove that _someone is smiling_

---

## Step 1: Represent in **First-Order Logic (FOL)**

Let’s define predicates:

- `Graduating(x)` – person `x` is graduating
    
- `Happy(x)` – person `x` is happy
    
- `Smiling(x)` – person `x` is smiling
    

### FOL Representations:

a) ∀x (Graduating(x) → Happy(x))  
b) ∀x (Happy(x) → Smiling(x))  
c) ∃x Graduating(x)

**Negated Goal (for resolution proof):**  
¬∃x Smiling(x) → equivalent to ∀x ¬Smiling(x)

---

## Step 2: Convert to **Conjunctive Normal Form (CNF)**

### a) ∀x (Graduating(x) → Happy(x))

→ Equivalent to: ∀x (¬Graduating(x) ∨ Happy(x))  
→ CNF: ¬Graduating(x) ∨ Happy(x)

### b) ∀x (Happy(x) → Smiling(x))

→ Equivalent to: ∀x (¬Happy(x) ∨ Smiling(x))  
→ CNF: ¬Happy(x) ∨ Smiling(x)

### c) ∃x Graduating(x)

→ Introduce a constant `a`: Graduating(a) (Skolemization)

### ¬Goal: ¬∃x Smiling(x)

→ Equivalent to: ∀x ¬Smiling(x)  
→ Instantiate with `a`: ¬Smiling(a)

---

## Step 3: All Clauses in CNF

1. ¬Graduating(x) ∨ Happy(x)
    
2. ¬Happy(x) ∨ Smiling(x)
    
3. Graduating(a)
    
4. ¬Smiling(a) ← negated goal
    

---

## Step 4: Resolution

### Resolution Step 1:

Clause 1: ¬Graduating(x) ∨ Happy(x)  
Clause 3: Graduating(a)  
**Unify x = a**  
→ Resolvent: Happy(a)

### Resolution Step 2:

Clause 2: ¬Happy(x) ∨ Smiling(x)  
New clause: Happy(a)  
**Unify x = a**  
→ Resolvent: Smiling(a)

### Resolution Step 3:

New clause: Smiling(a)  
Clause 4: ¬Smiling(a)  
→ Resolvent: **Empty clause (⊥)** ⇒ Contradiction

---

## Step 5: Resolution Tree

```
                (⊥)
               /   \
     Smiling(a)   ¬Smiling(a)
        |
   Happy(a), ¬Happy(x) ∨ Smiling(x)
        |
Graduating(a), ¬Graduating(x) ∨ Happy(x)
        |
    Graduating(a)
```

---

## Final Conclusion:

Since the **negation of the goal leads to contradiction**,  
**the original goal is proven:**

> **∃x Smiling(x)** → **Someone is smiling**

✅ **Q.E.D.**

# Example 2

What actions would you take to prove “Some who are intelligent can’t read” using
propositional logic:
a) Whoever can read is literate
b) Dolphins are not literate
c) Some dolphins are intelligent

### **Given statements:**

**a)** Whoever can read is literate  
**b)** Dolphins are not literate  
**c)** Some dolphins are intelligent

### **Step 1: Represent using Propositional Logic**

Let’s define:

- `CanRead(x)` – x can read
    
- `Literate(x)` – x is literate
    
- `Intelligent(x)` – x is intelligent
    
- `Dolphin(x)` – x is a dolphin
    
- Use a specific dolphin `d` for existential reasoning (Skolemization)
    

**FOL Representations:**

1. ∀x (CanRead(x) → Literate(x)) → (¬CanRead(x) ∨ Literate(x))
    
2. ¬Literate(d) – Some dolphin is not literate
    
3. Intelligent(d) ∧ Dolphin(d)
    

---

### **Goal:**

Prove ∃x (Intelligent(x) ∧ ¬CanRead(x))

That is, **some intelligent being cannot read**

---

### **Step 2: Reasoning**

From (1):  
¬CanRead(d) ∨ Literate(d)  
But (2): ¬Literate(d)

**Resolution:**  
From ¬CanRead(d) ∨ Literate(d)  
and ¬Literate(d)  
→ Resolves to ¬CanRead(d)

From (3): Intelligent(d)  
We now have: Intelligent(d) ∧ ¬CanRead(d)  
⇒ ∃x (Intelligent(x) ∧ ¬CanRead(x)) — **Goal is proved**

---

# Example 3

Consider the following facts:
a) Steve only likes easy courses.
b) Science courses are hard.
c) All the courses in the basket _ weaving department are easy.
d) BK301 is a basket _ weaving course.
Find by resolution that “What course would Steve like?

### **Given Facts:**

a) Steve only likes easy courses.  
b) Science courses are hard.  
c) All courses in the basket weaving department are easy.  
d) BK301 is a basket weaving course.

---

### **Step 1: Represent in Propositional Logic**

Define predicates:

- `Likes(Steve, x)` – Steve likes course x
    
- `Easy(x)` – x is easy
    
- `Hard(x)` – x is hard
    
- `Science(x)` – x is a science course
    
- `BasketWeaving(x)` – x is a basket weaving course
    
- Let `BK301` be a course
    

---

### **FOL Translations:**

1. ∀x (Likes(Steve, x) → Easy(x)) → ¬Likes(Steve, x) ∨ Easy(x)
    
2. ∀x (Science(x) → Hard(x))
    
3. ∀x (BasketWeaving(x) → Easy(x))
    
4. BasketWeaving(BK301)
    

---

### **Goal:** Find course(s) such that Steve likes them.

From (4): BK301 is a basket weaving course  
→ From (3): BasketWeaving(BK301) → Easy(BK301)  
→ Easy(BK301)

Now, from (1): Steve only likes easy courses  
So if Easy(BK301), then Likes(Steve, BK301) is **possible**

Hence, **BK301** is a course that **Steve would like**

---

### **Answer:**

Steve would like **BK301**.