# Introduction to cryptography

Book: Douglas Stinson Cryptography: Theory & practice (3rd edition)
Book The art of deception

### Terminology

- Plaintext
- Ciphertext
- Encryption
- Decryption
- Cipher (method of writing I.e encryption scheme)
- Cryptography (science & art of deigning ciphers)
- Cryptanalysis (science & art of breaking ciphers)
- Cryptology (study of Cryptography & Cryptanalysis)

### Ciphers vs. Codes

Cipher -> mathematical transformation
Codes -> a code-book

# CyptoSystem

### Definition

- P possible plaintexts
- C possible ciphertexts
- K key space
- E encryption alogrithm
- D decryption algorithm

for each k from K, there exists a Ek: P -> C and Dk : C -> P so that
whateer x from P Dk(Ek(x)) = x

You sned Ek(x) and apply Dk so that you get Dk(Ek(x)) = x

### Requirements:

- Efficient for all keys
- Easy to use
- Security of the system should depend on the secrecy of the keys (Kerchoff's principle)

- Confidientilatiy
- Integrity
- Authenticity
- Non-repudiation : avoiding denial or disowning of a contract. It should not be possible to backtrack.


Stenography : hide communication
Cryptography : visible but scrambled

