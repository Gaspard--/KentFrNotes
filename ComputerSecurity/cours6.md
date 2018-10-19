# Asymetric Cryptography
 aka pulbic / two key cryptography

- Motivation problem: key distribution
- Proposed by Diffie and Hellman

PK, SK
whtever X of the pliantext space, {{x}PK}SK == x

Euler's totient function the number of integers <= m and co-prime with m
 example:
 6 -> 2 (1 and 5)
 11 -> 10 (all numbers are coprime since 11 is prime)

If p is prime f(p) -> p - 1
If m is a product of 2 prime numbers p and q, f(m) = (p - 1) * (q - 1)

9 -> 3 * 3 -> f(9) = 2 * 2 = 4
{1, 2, 4, 5, 7, 8} -> 6

OWF - discrete logatihms is hard

# Diffie Hellman key exchange

- weak to MITM attack

Alce chooses x in {2, .. p - 1}
m1 = a^x (mod p)
Bob chooses y in {2, ... p - 1}
m2 = a^y (mod p)

The both exponentiate again to obtain
a ^ (x * y) = a ^ (y * x)

# RSA
Find 2 prme numbers p and q, let n = p * q
Find an integer e rlatively prime to

euler_totient_function(n) = (p - 1)(a - 1)

Find an integer d such that:

e * d === 1 (mod euler_totient_function(n))

Make n and e public, p q and d kept secret.

Anyone can encrypt a message m in [0, n - 1]

c = m ^ e (mod n)

decryption

c ^ d = m ^ (e * d) (mod n) = m (mod n)