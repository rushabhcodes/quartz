---
created: 2025-05-10T19:42
updated: 2025-05-10T22:49
---
To represent the **flat tire replacement problem** in **Action Description Language (ADL)**—a formal language used in AI planning—we’ll define:

1. **Initial state**
    
2. **Goal state**
    
3. **Actions** with:
    
    - Preconditions
        
    - Effects (add and delete)
        

---

### 🛠️ **Problem Summary:**

- **Initial State**: Flat tire on car, spare in trunk.
    
- **Goal**: Spare tire mounted on axle.
    

---

### 🧩 **1. Predicates**

We’ll define the world using logical predicates:

```prolog
(on ?tire ?location)       ; Tire is on some location (axle, trunk, ground)
(is-flat ?tire)            ; Tire is flat
(is-spare ?tire)           ; Tire is a spare
(clear ?location)          ; The location is empty (e.g., axle is clear)
(in-trunk ?tire)           ; Tire is in trunk
```

---

### 🧱 **2. Initial State (Facts)**

```prolog
(on flat_tire axle)
(is-flat flat_tire)
(on spare_tire trunk)
(is-spare spare_tire)
(clear ground)
```

---

### 🎯 **3. Goal State**

```prolog
(on spare_tire axle)
```

---

### 🏁 **4. Actions (ADL style)**

#### ✅ Action 1: `Remove flat tire`

```prolog
Action: remove-flat
Preconditions:
    (on flat_tire axle)
    (is-flat flat_tire)
    (clear ground)
Effects:
    (not (on flat_tire axle))
    (on flat_tire ground)
    (clear axle)
```

---

#### ✅ Action 2: `Get spare from trunk`

```prolog
Action: get-spare
Preconditions:
    (on spare_tire trunk)
    (is-spare spare_tire)
    (clear ground)
Effects:
    (not (on spare_tire trunk))
    (on spare_tire ground)
```

---

#### ✅ Action 3: `Mount spare`

```prolog
Action: mount-spare
Preconditions:
    (on spare_tire ground)
    (clear axle)
Effects:
    (not (on spare_tire ground))
    (on spare_tire axle)
    (not (clear axle))
```

---

### 🧠 **5. Discussion of the Solution (Plan)**

A valid plan to solve the problem:

1. **remove-flat**: Remove the flat tire from the axle and place it on the ground.
    
2. **get-spare**: Take the spare tire from the trunk and place it on the ground.
    
3. **mount-spare**: Mount the spare tire on the axle.
    

---

### ✅ Final Goal Achieved:

- `spare_tire` is now **on the axle**.
    
- Flat tire is on ground.
    
- Trunk is empty.
    

This formal representation helps **AI planners** break down real-world problems into solvable steps using logic and constraints.