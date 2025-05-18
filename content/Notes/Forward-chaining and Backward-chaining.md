---
created: 2025-05-19T01:53
updated: 2025-05-19T01:54
---
## 1. Forward-Chaining Algorithm

### Definition:

**Forward-Chaining** is a data-driven inference method.  
It starts from known facts and applies rules to infer new facts until the goal is reached (or no more inferences can be made).

### How it works:

1. Start with a set of **facts** (knowledge base).
    
2. Apply all rules whose **preconditions match the current facts**.
    
3. **Add the rule’s conclusions** (new facts) to the knowledge base.
    
4. Repeat until:
    
    - The **goal is inferred**, or
        
    - No more rules can be applied.
        

### Example:

**Facts**:

- Sun is shining → Sunny
    
- Sunny → Go outside
    
- Go outside → Happy
    

**Initial Fact**:

- Sun is shining
    

**Goal**:

- Happy
    

**Inference**:

1. Sun is shining → infer Sunny
    
2. Sunny → infer Go outside
    
3. Go outside → infer Happy
    

Goal is reached.

### Advantages:

- Suitable when all data is known upfront.
    
- Works well in real-time systems, such as expert systems and diagnostics.
    

---

## 2. Backward-Chaining Algorithm

### Definition:

**Backward-Chaining** is a goal-driven inference method.  
It starts with the goal and works backward to determine what facts must be true to satisfy that goal.

### How it works:

1. Start with a **goal**.
    
2. Look for rules that can produce that goal in the **conclusion**.
    
3. Make the **preconditions of that rule** the new subgoals.
    
4. Repeat the process until you reach **known facts** or fail.
    

### Example:

**Rules**:

- Sunny → Go outside
    
- Go outside → Happy
    
- Sun is shining → Sunny
    

**Goal**:

- Happy
    

**Inference**:

1. To prove `Happy`, need `Go outside`
    
2. To prove `Go outside`, need `Sunny`
    
3. To prove `Sunny`, need `Sun is shining`
    

If `Sun is shining` is known, then the goal `Happy` is provable.

### Advantages:

- Efficient when the goal is known, and you want to verify if it can be satisfied.
    
- Used in logic programming (e.g., Prolog), theorem proving, and question answering systems.
    

---

## Forward vs Backward Chaining

|Feature|Forward-Chaining|Backward-Chaining|
|---|---|---|
|Approach|Data-driven|Goal-driven|
|Starts from|Known facts|Desired conclusion|
|Stops when|Goal is derived|Facts supporting goal are found|
|Use Case|Expert systems, diagnosis|Logic programming, proof systems|
|Direction|Bottom-up inference|Top-down reasoning|

---

## Summary

- **Forward-Chaining**: Pushes known facts forward to derive conclusions.
    
- **Backward-Chaining**: Pulls from the goal backward to verify if facts can support it.
    

Both are fundamental to AI reasoning, rule-based systems, and knowledge inference.