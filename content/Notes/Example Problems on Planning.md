---
created: 2025-05-19T01:24
updated: 2025-05-19T01:31
---
# Example 1

## Design a planning problem using STRIP for Air cargo transport. It involves loading and unloading cargo onto and of planes and flying it from place.
## Initial state: At SFO airport, Cargo1, Plane1 and at JFK airport, Cargo2, Plane2 is present.
## Goal state: At SFO airport Cargo2 and at JFK airport Cargo1 is present.

### 🔹 **1. Define Predicates**

These describe the facts of the world:

- `At(x, y)` – Object `x` is at location `y`
    
- `In(c, p)` – Cargo `c` is inside Plane `p`
    
- `Cargo(x)` – `x` is a cargo
    
- `Plane(x)` – `x` is a plane
    
- `Airport(x)` – `x` is an airport
    

---

### 🔹 **2. Initial State**

```plaintext
At(Cargo1, SFO)
At(Plane1, SFO)
At(Cargo2, JFK)
At(Plane2, JFK)
Cargo(Cargo1)
Cargo(Cargo2)
Plane(Plane1)
Plane(Plane2)
Airport(SFO)
Airport(JFK)
```

---

### 🔹 **3. Goal State**

```plaintext
At(Cargo1, JFK)
At(Cargo2, SFO)
```

---

### 🔹 **4. Actions**

#### (a) Load(c, p, a)

```plaintext
Preconditions:
  At(c, a) AND At(p, a)
  Cargo(c)
  Plane(p)
  Airport(a)

Effects:
  Add: In(c, p)
  Del: At(c, a)
```

#### (b) Unload(c, p, a)

```plaintext
Preconditions:
  In(c, p)
  At(p, a)
  Cargo(c)
  Plane(p)
  Airport(a)

Effects:
  Add: At(c, a)
  Del: In(c, p)
```

#### (c) Fly(p, from, to)

```plaintext
Preconditions:
  At(p, from) AND Plane(p) AND Airport(from) AND Airport(to)

Effects:
  At(p, to) AND - At(p, from)
```

---

### 🔹 **5. Plan Overview (One Possible Sequence)**

To achieve the goal state:

1. `Load(Cargo1, Plane1, SFO)`
    
2. `Fly(Plane1, SFO, JFK)`
    
3. `Unload(Cargo1, Plane1, JFK)`
    
4. `Load(Cargo2, Plane2, JFK)`
    
5. `Fly(Plane2, JFK, SFO)`
    
6. `Unload(Cargo2, Plane2, SFO)`
    

---

This formalizes the **STRIPS planning problem** for air cargo transport involving **loading, unloading, and flying planes** to meet the goal state. Let me know if you’d like this converted into PDDL format too.

