---
created: 2025-05-19T01:24
updated: 2025-05-19T01:42
---
# Example 1

Design a planning problem using STRIP for Air cargo transport. It involves loading and unloading cargo onto and of planes and flying it from place.
Initial state: At SFO airport, Cargo1, Plane1 and at JFK airport, Cargo2, Plane2 is present.
Goal state: At SFO airport Cargo2 and at JFK airport Cargo1 is present.

### **1. Define Predicates**

These describe the facts of the world:

- `At(x, y)` – Object `x` is at location `y`
    
- `In(c, p)` – Cargo `c` is inside Plane `p`
    
- `Cargo(x)` – `x` is a cargo
    
- `Plane(x)` – `x` is a plane
    
- `Airport(x)` – `x` is an airport
    

---

### **2. Initial State**

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

### **3. Goal State**

```plaintext
At(Cargo1, JFK)
At(Cargo2, SFO)
```

---

### **4. Actions**

#### (a) Load(c, p, a)

```plaintext
Preconditions:
  At(c, a) ∧ At(p, a) ∧ Cargo(c) ∧ Plane(p) ∧ Airport(a)

Effects:
  In(c, p) ∧ ¬At(c, a)
```

#### (b) Unload(c, p, a)

```plaintext
Preconditions:
  In(c, p) ∧ At(p, a) ∧ Cargo(c) ∧ Plane(p) ∧ Airport(a)

Effects:
  At(c, a) ∧ ¬In(c, p)
```

#### (c) Fly(p, from, to)

```plaintext
Preconditions:
  At(p, from) ∧ Plane(p) ∧ Airport(from) ∧ Airport(to)

Effects:
  At(p, to) ∧ ¬At(p, from)
```

---

### **5. Plan Overview (One Possible Sequence)**

To achieve the goal state:

1. `Load(Cargo1, Plane1, SFO)`
    
2. `Fly(Plane1, SFO, JFK)`
    
3. `Unload(Cargo1, Plane1, JFK)`
    
4. `Load(Cargo2, Plane2, JFK)`
    
5. `Fly(Plane2, JFK, SFO)`
    
6. `Unload(Cargo2, Plane2, SFO)`
    

# Example 2

Consider problem of changing a flat tire. The goal is to have a good spare tire properly
mounted on to the car’s axle, where the initial state has a flat tire on the axle and a good spare tire in the trunk. Give the ADL description for the problem and also discuss the solution.

## Problem: Changing a Flat Tire

### **Initial State**

- `On(FlatTire, Axle)` – Flat tire is mounted on the axle
    
- `In(SpareTire, Trunk)` – Spare tire is inside the trunk
    
- `Tire(FlatTire)`, `Tire(SpareTire)`
    
- `Spare(SpareTire)`
    
- `WrenchAvailable`, `JackAvailable`, `Loose(FlatTire)` is `False` initially
    
- `Removed(FlatTire)` is `False` initially
    
- `Mounted(SpareTire)` is `False` initially
    

---

### **Goal State**

- `Mounted(SpareTire)`
    
- `¬On(FlatTire, Axle)`
    
- `¬In(SpareTire, Trunk)`
    

---

## ADL Description

### 1. **Remove(FlatTire, Axle)**

```adl
Preconditions:
  On(FlatTire, Axle) ∧ Loose(FlatTire)

Effects:
  ¬On(FlatTire, Axle)
  ∧ Removed(FlatTire)
```

---

### 2. **Loosen(FlatTire)**

```adl
Preconditions:
  On(FlatTire, Axle) ∧ WrenchAvailable

Effects:
  Loose(FlatTire)
```

---

### 3. **GetSpare(SpareTire)**

```adl
Preconditions:
  In(SpareTire, Trunk)

Effects:
  ¬In(SpareTire, Trunk)
```

---

### 4. **Mount(SpareTire, Axle)**

```adl
Preconditions:
  Removed(FlatTire) ∧ ¬On(FlatTire, Axle) ∧ ¬In(SpareTire, Trunk)

Effects:
  On(SpareTire, Axle)
  ∧ Mounted(SpareTire)
```

---

## Solution Steps (Valid Plan)

1. `Loosen(FlatTire)` – Loosen the flat tire bolts
    
2. `Remove(FlatTire, Axle)` – Take off the flat tire
    
3. `GetSpare(SpareTire)` – Take the spare tire out of the trunk
    
4. `Mount(SpareTire, Axle)` – Mount the spare tire on the axle
    