#### **Introduction:**

The **Diffie-Hellman Key Exchange** is a cryptographic method that allows two parties to establish a shared secret over an insecure channel. While the protocol allows secure key exchange, it is **vulnerable to a Man-in-the-Middle (MITM) attack** if the identities of the communicating parties are not authenticated.

#### **How Diffie-Hellman Works (Briefly):**

Let:

- `g` be a public base (generator),
    
- `p` be a large prime number (public modulus),
    
- Alice chooses a private key `a`, computes `A = g^a mod p`,
    
- Bob chooses a private key `b`, computes `B = g^b mod p`.
    

Then they exchange `A` and `B` and compute the shared key:

- Alice computes `K = B^a mod p`,
    
- Bob computes `K = A^b mod p`.
    

Since `g^(ab) mod p = g^(ba) mod p`, both arrive at the same shared key.