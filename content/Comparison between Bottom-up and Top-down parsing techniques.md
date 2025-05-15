---
created: 2025-05-14T22:36
updated: 2025-05-14T22:36
---
| **Aspect**                       | **Top-Down Parser**                                                        | **Bottom-Up Parser**                                             |
| -------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Definition**                   | Starts parsing from the start symbol and tries to derive the input string. | Starts from the input string and reduces it to the start symbol. |
| **Parsing Direction**            | Left to right on the input; derivation is **leftmost**.                    | Left to right on input; derivation is **rightmost in reverse**.  |
| **Parse Tree Construction**      | From **root to leaves** (top-down).                                        | From **leaves to root** (bottom-up).                             |
| **Grammar Used**                 | **LL(k)** grammar (subset of CFG).                                         | **LR(k)** grammar (superset of LL grammars).                     |
| **Backtracking**                 | May require backtracking (unless predictive).                              | No backtracking required.                                        |
| **Error Detection**              | Detects errors early (near the root of the parse tree).                    | Detects errors late (closer to the leaves of the tree).          |
| **Complexity of Implementation** | Easier to implement manually (e.g., recursive descent).                    | Harder to implement manually; generally uses tools.              |
| **Examples**                     | Recursive Descent, Predictive Parser (LL Parser)                           | Shift-Reduce, LR, SLR, LALR parsers                              |
|                                  |                                                                            |                                                                  |
### Example

For an expression like `a + b * c`

- **Top-Down Parser**:  
    Starts from expression rule and predicts what production to apply based on lookahead symbols.

- **Bottom-Up Parser**:  
    Starts by shifting `a`, then `+`, then reduces `b * c` as a term, then combines with `a`.
### Summary

- Use **Top-down** when grammar is simple and recursive.
    
- Use **Bottom-up** for more powerful grammar support and better error handling.