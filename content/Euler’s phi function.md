### **Rules for Finding Euler’s Phi Function (φ(n))**

Euler’s phi (φ) function, also called Euler’s totient function, counts the number of positive integers less than or equal to `n` that are **coprime to `n`** (i.e., integers whose greatest common divisor (GCD) with `n` is 1).

---

### **Rules for Computing φ(n):**

1. **If `n` is a prime number:**
    
    $\phi(n) = n - 1$
    
    Because all integers less than a prime number are coprime to it.
    
    **Example:**
    
    $phi(7) = 7 - 1 = 6$

---

2. **If `n = p^k`, where `p` is a prime and `k ≥ 1`:**
    
	$phi(p^k) = p^k - p^{k-1} = p^k \left(1 - \frac{1}{p}\right)$
    
    **Example:**
    
    $\phi(2^3) = 8 - 4 = 4$

---

3. **If `n` is a product of two or more **distinct** prime numbers:**
    
    $\phi(n) = n \left(1 - \frac{1}{p_1}\right)\left(1 - \frac{1}{p_2}\right)\cdots\left(1 - \frac{1}{p_k}\right)$
    
    Where `p₁, p₂, ..., pₖ` are the distinct prime factors of `n`.
    
    **Example:**
    
    $\phi(15) = 15 \left(1 - \frac{1}{3}\right)\left(1 - \frac{1}{5}\right) = 15 × \frac{2}{3} × \frac{4}{5} = 8$

---

4. **φ is multiplicative for coprime integers:**  
    If `a` and `b` are **coprime**, then:
    
    $\phi(a \cdot b) = \phi(a) \cdot \phi(b)$
    
    **Example:**
    
    $\phi(9) = 6,\ \phi(10) = 4\ \Rightarrow \phi(90) = \phi(9 × 10) = 6 × 4 = 24$

---

### **Steps to Compute φ(n):**

1. Factorize `n` into its prime factors.
    
2. Apply the formula:
    
    $\phi(n) = n \prod_{i=1}^{k} \left(1 - \frac{1}{p_i}\right)$

---

Let me know if you want examples with large numbers or Python code to compute it automatically.