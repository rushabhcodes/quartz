---
created: 2025-05-19T02:10
updated: 2025-05-19T02:10
---
| **Feature**         | **Uninformed Search**                 | **Informed Search**                                       |
| ------------------- | ------------------------------------- | --------------------------------------------------------- |
| **Also Known As**   | Blind Search                          | Heuristic Search                                          |
| **Uses Heuristic?** | ❌ No                                  | ✅ Yes (`h(n)` function used)                              |
| **Guidance**        | No knowledge about goal direction     | Uses domain-specific knowledge to guide search            |
| **Goal Direction**  | Explores blindly                      | Goal-directed exploration                                 |
| **Efficiency**      | Less efficient, explores more nodes   | More efficient with a good heuristic                      |
| **Optimality**      | Only UCS is optimal                   | A* is optimal with admissible heuristic                   |
| **Completeness**    | BFS, UCS are complete                 | A*, Greedy Best-First can be complete (depends on `h(n)`) |
| **Time & Space**    | High due to exhaustive search         | Lower (if heuristic is good)                              |
| **Examples**        | BFS, DFS, UCS, DLS, IDDFS             | A*, Greedy Best-First, RBFS, IDA*                         |
| **Use Case**        | When no domain knowledge is available | When domain knowledge or heuristics are available         |