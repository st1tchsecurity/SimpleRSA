# SimpleRSA
A simple pythonic implementation of RSA cryptography.

# What is RSA?
RSA, named after its inventors Rivest, Shamir, and Adleman, is a public-key cryptosystem widely used for secure data transmission. In the RSA system, encryption keys are public, while the decryption keys are kept secret (private). 
This asymmetry is based on the practical difficulty of factoring the product of two large prime numbers, the factoring problem.

# How does RSA work?
**Here’s a step-by-step breakdown of how RSA works:**

**Choose two distinct prime numbers p and q:** These numbers are kept secret.

**Compute n = pq:** The product of these two primes (n) is used as the modulus for both the public and private keys. Its length, usually expressed in bits, is the key length.

**Compute the totient, φ(n) = (p-1)(q-1):** The totient of n, φ(n), is an important number in number theory. It is used in the definition of the RSA system.

**Choose an integer e such that 1 < e < φ(n) and gcd(e, φ(n)) = 1:** This number e is the public key exponent and it must be coprime with φ(n).

**Compute d to satisfy the congruence relation de ≡ 1 (mod φ(n)):** This is the private key exponent. It is calculated using the modular multiplicative inverse of e mod φ(n).

# Now, let’s look at how encryption and decryption work

**Encryption:** Given a plaintext message m, the ciphertext c is obtained by c = m^e mod n.

**Decryption:** Given the ciphertext c, the plaintext message m can be recovered by m = c^d mod n.

# Implementing RSA in Python
In Python, we can define a class RSA with methods for encryption and decryption. The __init__ method calculates and stores the necessary parameters (n, φ(n), e, d) for these operations. 
The encrypt and decrypt methods implement the encryption and decryption formulas respectively. We use the built-in pow function with three arguments (base, exponent, modulus) for these calculations, 
which is more efficient than using the ** operator and the % operator separately.
