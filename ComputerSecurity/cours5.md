# Symmetric Cryptography

one/secret/private key cryptography

Either only one key or the dervption key is easilly obtained from the other key

Advantages:
- typically very efficient and faster to execute
Desadvantage:
- key distribution issue
  - `n * (n - 1) / 2` keys are needed for n aprties

Block vs stream:
Input | arbitraily long key & plaintext stream | a bloack of plaintext f a precise size and a key
output | based on internal state, changes as cipher operates | a block of ciphertext of the same size of the plaintext
strength | typically aster and have lower hardware complexity | transmission error in one block does not affect other blocks
Weakness | Susceptibl  to security problems if used incorreectly | susceptible to cryptanalysis

## Stream ciphers

Break plaintext into succesive bits.
Key stream
Encrypt each pi with key stream element Ki
Ek(P) = Ek1(P1)Ek2(p2)...
typically uses xor


Synchronous stream ciphers:
 - key stream generated independently
Selfsynchronous stream ciphers
 - key derived from preceding ciphertext

## Block ciphers

Okaintext size n;
key size k;
n and k are not necessarily equal.

Typcally block size < plaintext size
Apply cipher repeatatidly.

Confusion: hides relationship between ciphertext and key
Diffusion: hides relationship between ciphertext and plaintext

Both hide statistical relationship.

### Product cipher:

Chains several fnction using different keys generated from a single key.

### AES

Won Nist competiti to find replacement for AES

## Modes of operation.

Howare blocks lined p.

Combine basic cipher + some sort of feedback + a simple operation
This deals with the block cipher's limitations:
- varying text size
- plain text may repeat

### CBC
 starts with initialisation vector IV.
 Applies operation on previous ciphertext or IV