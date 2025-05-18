---
created: 2025-05-19T01:38
updated: 2025-05-19T01:42
---
### PAC Learning: _Probably Approximately Correct Learning_

**PAC learning** is a framework in computational learning theory introduced by **Leslie Valiant** in 1984. It formalizes the idea of learning from examples and quantifies how many examples are needed to learn a good approximation of the target function with high confidence.

---

### Key Concepts

1. **Probably** – The learner will succeed with high probability (e.g., 95% confidence).
    
2. **Approximately Correct** – The learned hypothesis will be close to the true function (within an error margin ε).
    

---

### Formal Definition

A concept class **C** is **PAC-learnable** if:

- For any concept $c \in C$
    
- For any distribution **D** over the input space
    
- For any $0 < \epsilon < 1$ (error tolerance)
    
- For any $0 < \delta < 1$ (confidence level)
    

There exists a learning algorithm **L** that, given a sufficient number of labeled training examples drawn from **D**, will with probability at least 1−δ1 - \delta, output a hypothesis **h** such that:

$P_{x \sim D}[h(x) \neq c(x)] \leq \epsilon$

---

### Sample Complexity

The number of examples needed is:

$m \geq \frac{1}{\epsilon} \left( \log |H| + \log \frac{1}{\delta} \right)$

Where:

- $m$: number of training examples
    
- $\epsilon$: allowable error
    
- $\delta$: allowable failure probability
    
- $|H|$: size of hypothesis space
    

---

### Intuition

PAC learning asks:

> "Can we find a hypothesis that is _probably_ (with confidence $1 - \delta$) _approximately correct_ (error $\leq \epsilon$)?"

If yes, the learning problem is **PAC-learnable**.

---

### Example

Say you're learning a spam filter:

- You want it to classify emails with at most 5% error (ε = 0.05).
    
- You want to be 99% sure it works as intended (δ = 0.01).
    
- PAC learning helps determine how many labeled emails are needed to train such a model.
    

---

### Summary

PAC learning:

- Provides **theoretical guarantees** on learning performance.
    
- Balances **accuracy** (ε) and **confidence** (δ).
    
- Helps estimate **how much data** is needed for reliable learning.
    

It is fundamental in understanding the limits and feasibility of machine learning algorithms.