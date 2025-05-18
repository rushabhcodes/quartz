---
created: 2025-05-16T10:37
updated: 2025-05-16T10:37
---

| **Aspect**                  | **Uninformed Search**                                                                         | **Informed Search**                                             |
| --------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Knowledge Required**      | No domain-specific knowledge; only knows the start and goal state                             | Uses domain-specific knowledge (heuristics) to guide the search |
| **Search Direction**        | Blindly explores the search space                                                             | Directed towards the goal using heuristics                      |
| **Efficiency**              | Less efficient, explores many irrelevant paths                                                | More efficient, focuses on promising paths                      |
| **Examples**                | - Breadth-First Search (BFS) - Depth-First Search (DFS) - Depth-Limited - Iterative Deepening | - Greedy Best-First Search - A* Search                          |
| **Use of Heuristics**       | ❌ Not used                                                                                    | ✅ Heuristic function `h(n)` used                                |
| **Completeness**            | Depends on the algorithm (e.g., BFS is complete)                                              | Depends on the heuristic used                                   |
| **Optimality**              | Some (like BFS and UCS) are optimal                                                           | A* is optimal if heuristic is admissible and consistent         |
| **Time & Space Complexity** | Generally higher than informed search                                                         | Usually lower due to guided exploration                         |
| **Goal Awareness**          | Goal is known but not used to guide search                                                    | Goal is used to estimate closeness from current state           |
### 📝 Summary
- **Uninformed Search** explores blindly without any additional knowledge.
- **Informed Search** uses **heuristics** to guide the search efficiently toward the goal.