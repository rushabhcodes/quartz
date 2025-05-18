---
created: 2025-05-19T01:48
updated: 2025-05-19T01:50
---
## 1. What is Hierarchical Planning?

In traditional planning (like STRIPS), a planner works directly with **primitive actions**.  
In **hierarchical planning**, we start with **high-level abstract tasks** and **decompose them** step-by-step into simpler tasks.

---

### 2. Key Concepts

|Term|Meaning|
|---|---|
|**Task**|Any activity that needs to be accomplished|
|**Primitive Task**|A task that can be executed directly (like `move(robot, A, B)`)|
|**Compound Task**|A higher-level task that needs to be broken into subtasks (like `buildHouse`)|
|**Task Network**|A set of tasks with temporal or ordering constraints|
|**Decomposition**|Process of refining a compound task into subtasks|
|**Methods**|Rules that specify how to decompose compound tasks|

---

### 3. How It Works

1. **Start with a high-level goal**
    
2. **Select a method** to decompose that goal
    
3. **Decompose compound tasks** into smaller subtasks (recursively)
    
4. **Repeat** until only primitive tasks remain
    
5. **Execute** the primitive actions in a valid order
    

---

### 4. Example: Building a House 🏠

#### High-Level Task:

```
BuildHouse
```

#### Method:

```
BuildHouse → [GetPermit, HireContractor, Construct, PayContractor]
```

#### Further Decomposition:

```
Construct → [LayFoundation, BuildWalls, InstallRoof]
```

Eventually:

```
InstallRoof → [OrderMaterials, HireRoofers, SuperviseInstallation]
```

These leaf-level tasks will eventually map to executable actions like:

```
Order(Materials, SupplierX), Pay(Contractor, Amount)
```

---

### 5. Benefits of Hierarchical Planning

**Scalability**: Reduces complexity by breaking large problems into manageable parts  
**Reusability**: Methods can be reused for similar tasks  
**Abstraction**: Focus on high-level strategy rather than low-level mechanics  
**Human-Like Reasoning**: Mimics how humans naturally plan complex tasks

---

### 6. Applications

- **Robotics**: e.g., plan to clean a house → clean rooms → sweep floor, etc.
    
- **Game AI**: NPC behaviors like "attack base" → move to location → fire weapon
    
- **Logistics**: Transporting goods → load → travel → unload
    
- **Workflow Management**: Business processes → customer onboarding → send welcome email, etc.
    

---

### 7. Challenges

**Choosing the Right Decomposition**: Multiple methods may apply; selecting the optimal one is non-trivial  
**Execution Monitoring**: Real-world tasks may fail; planner must adapt  
**Complex Constraints**: Handling preconditions and interactions between subtasks is difficult

---

### Summary Table

|Feature|Hierarchical Planning|
|---|---|
|Task Type|Compound and primitive|
|Core Mechanism|Task decomposition|
|Knowledge Used|Domain-specific methods|
|Planning Granularity|High-level to low-level|
|Analogy|Project breakdown into subtasks|
|Strength|Efficient for complex domains|

---

**Hierarchical Planning** offers a structured and efficient approach for solving real-world planning problems by "thinking big, and refining down." It blends symbolic planning with abstraction and is key to many modern AI systems.