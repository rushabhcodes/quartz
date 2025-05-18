---
created: 2025-05-19T02:11
updated: 2025-05-19T02:12
---
### **Depth-Limited Search (DLS)**

#### Definition:

Depth-Limited Search is a variant of **Depth-First Search (DFS)** where the search is limited to a specific **depth `l`** (i.e., the number of levels it can go down in the search tree).

#### Key Features:

|Feature|Description|
|---|---|
|**Limit (`l`)**|Maximum depth the algorithm will explore.|
|**Completeness**|No (if the solution is beyond limit).|
|**Optimality**|No|
|**Time Complexity**|O(bl)|
|**Space Complexity**|O(l)|
|**Used When**|You know the depth of the solution.|

#### Example Use:

- Searching a tree up to depth 3, ignoring all nodes beyond it.
    

#### Problems:

- If the goal lies beyond the depth limit, it won't be found.
    

---

### **Depth-First Iterative Deepening Search (DFID or IDDFS)**

#### Definition:

IDDFS combines the space-efficiency of DFS and the completeness of BFS. It repeatedly performs DLS with increasing depth limits until the goal is found.

#### How it Works:

1. Perform DLS with depth = 0
    
2. Then depth = 1, then 2, and so on...
    
3. Stop when the goal is found.
    

#### Key Features:

|Feature|Description|
|---|---|
|**Completeness**|✅ Yes|
|**Optimality**|✅ Yes (if step cost is uniform)|
|**Time Complexity**|O(bd)|
|**Space Complexity**|O(d)|
|**Used When**|Depth is unknown but memory is limited.|

#### Example Use:

- Solving puzzles (like 8-puzzle), where depth is unknown.
    

#### Advantages:

- Finds shallowest solution first.
    
- Uses less memory than BFS.
    

---

### **DLS vs IDDFS – Comparison Table**

|**Feature**|**DLS**|**IDDFS**|
|---|---|---|
|Search Strategy|DFS with depth limit|Repeated DLS with increasing limits|
|Depth Knowledge|Required|Not required|
|Completeness|No (if goal > limit)|✅ Yes|
|Optimality|❌ No|✅ Yes (with uniform cost)|
|Time Complexity|O(bl)|O(bd)|
|Space Complexity|O(l)|O(d)|
|Use Case|When depth is known|When depth is unknown and memory is limited|
