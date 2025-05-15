---
created: 2025-05-15T10:52
updated: 2025-05-15T10:54
---
#### **Definition**

The **Euclidean Algorithm** is a method for finding the **Greatest Common Divisor (GCD)** of two integers. The GCD of two numbers is the largest number that divides both of them without leaving a remainder.

---

#### **Purpose**

To compute `gcd(a, b)` for any two non-negative integers `a` and `b`, where `a ≥ b`.

---

#### **Working Principle**

The Euclidean Algorithm is based on the principle that:

> **gcd(a, b) = gcd(b, a mod b)**

This means that the GCD of two numbers does not change if the larger number is replaced by its remainder when divided by the smaller number.

---

#### **Algorithm Steps**

1. Given two integers `a` and `b` where `a ≥ b > 0`.
    
2. Compute `r = a mod b`.
    
3. Replace `a` with `b`, and `b` with `r`.
    
4. Repeat steps 2–3 until `r = 0`.
    
5. When `r = 0`, the GCD is the current value of `b`.
    

---

#### **Example**

Find `gcd(48, 18)` using the Euclidean Algorithm:

```python
Step 1: a = 48, b = 18
        48 mod 18 = 12   →  gcd(48, 18) = gcd(18, 12)

Step 2: a = 18, b = 12
        18 mod 12 = 6    →  gcd(18, 12) = gcd(12, 6)

Step 3: a = 12, b = 6
        12 mod 6 = 0     →  gcd(12, 6) = 6

Result: gcd(48, 18) = 6
```

---

#### **Applications**

- Cryptography (e.g., [[RSA]] algorithm)
    
- Simplifying fractions
    
- Modular arithmetic
    
- Finding multiplicative inverses (Extended Euclidean Algorithm)
    

---

#### **Advantages**

- Efficient and fast
    
- Requires only division and remainder operations
    
- Can be extended to find coefficients of Bézout's identity: `ax + by = gcd(a, b)` (used in modular inverse computation)
    

---

### **Conclusion**

The **Euclidean Algorithm** is a fundamental and efficient method in number theory for calculating the GCD of two integers. Its simplicity and effectiveness make it a key component in many areas of computer science and cryptography.