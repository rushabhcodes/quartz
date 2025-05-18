---
created: 2025-05-19T02:13
updated: 2025-05-19T02:16
---
### **Simulated Annealing (SA)**

**Simulated Annealing** is a probabilistic optimization algorithm inspired by the **annealing process in metallurgy**, where materials are heated and then slowly cooled to reduce defects and reach a more stable (minimum energy) state.

---

### **Core Idea:**

Simulated Annealing allows **occasional worse moves** (i.e., lower-quality solutions) to **escape local optima** early in the search. The probability of accepting worse solutions **decreases over time** (as the "temperature" drops).

---

### **Algorithm Steps:**

1. **Start** with an initial solution and high "temperature" `T`.
    
2. **Repeat** until system cools:
    
    - Generate a **neighboring solution**.
        
    - Calculate the **change in cost** (ΔE = new - current).
        
    - If ΔE < 0 (better), **accept the move**.
        
    - If ΔE ≥ 0 (worse), accept with probability:
        
        $P = e^{-\Delta E / T}$
    - **Cool down** the temperature:
        
        $T = T \times \text{cooling rate} \ (\text{e.g., } 0.95)$
3. Return the best solution found.
    

---

### **Why It Works:**

- Allows random exploration initially (due to high temperature).
    
- Gradually becomes more selective, like hill climbing.
    
- **Escapes local optima** by occasionally accepting bad moves.
    

---

### **Advantages:**

- Escapes local maxima/minima.
    
- Good for large, complex search spaces.
    
- Easy to implement.
    

### **Disadvantages:**

- Requires careful tuning of temperature and cooling rate.
    
- Slower than greedy algorithms.
    