# Cryptography Protocols & Applcations

## Cryptography Protocols

- Uses cryptographic mechanisms / primitives
  - encryption algorithm
  - digital signatures
  - hashing

Example:

Challenge/response protocols
- prob. easiest & simplest of sec. protocol
- Simple friend or for password challnge
- Vulnerable to replay
- More sophisticated
  - Issue a challenge: a fresg random value (a nonce)
  - responder transforms and gives back result (using aggreed upon key)
Nonces: "For the nonce" -> for the time being
 - must be unpredictable / unique
 - if transformation is public, only freshness is garantied

# Key Exchange and Entity Authentication

- Two levels of kets:
  - Master keys: long lived secret
  - Session keys: only valid for a short time
    - often symtric (faster)
Symmetric encryption is usually more efficient


Entity Authenticitation
- Prevent impersonation
  - MITM attack
  - Replay attack
- Replay attack preventable by varying the signed message

Trust third party:
Trent or *T*
- Each client shares a secret key with Trentxs
- Trent creates random session key

Example: Kerberos

A->T: A, B, Na
T->A: {Na, B, K, {A, K}(Kb)}(Ka)
A->B, {A, K}(Kb)
B->A, {Nb}(K)
A->B, {Nb - 1}(K)

Nssk to the Denning Sacco attack:
- Replay attack since bob has no garanty of freshness
- Kerberos by using timestamps to solve this problem
  -> Need to able to ensure integrety

# Digital signtures
Prove origin & authenticity of message

Alics has SKa and PKa.
- Encrypt M with her secret message
  - only Alice can do this
  - everyone can verifie origin of message using the public key
- if the message sign, the crypto hash of it

Digital signatures can be used to avoid mitm attacks.

# Cryptographic hash functions

let f be a "Cryptographic hash functions"
- Preimage restant: needs to be hard to find y so thats f(y) = x
- Collision resistant: needs to be hard to find x, y and y so that f(y) = f(x)

How to verifie that you have the public key fir Alice
PKI: public key infrastructure
-> often based ib some TTP called a Certificate Authority (CA)


