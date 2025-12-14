
RSA is a widely used public-key cryptosystem that relies on the mathematical properties of modular arithmetic and prime numbers. It enables secure communication over insecure channels, allowing for both encryption and digital signatures.

**Public-Key Cryptosystems:**

![[Pasted image 20251112141929.png|590]]

In a public-key cryptosystem, each participant has a pair of keys: a public key ( for Bob) and a private key ( for Bob). The public key can be freely distributed, while the private key must be kept secret. Anyone can encrypt a message using the recipient’s public key, but only the recipient, possessing the corresponding private key, can decrypt the message. **Crucially, while the channel itself may be insecure, an authentic channel for distributing public keys is essential for the security of the system.** If an adversary can tamper with the public key distribution, they can substitute their own public key, allowing them to intercept and decrypt messages intended for the original recipient.

**RSA Algorithm:**

![[Pasted image 20251112141950.png|538]]

The RSA algorithm involves the following steps:

1. **Key Generation:**
    - Alice generates two large prime numbers, $p$ and $q$.
    - She computes $n=pq$ and $ϕ(n)=(p−1)(q−1)$.
    - Alice selects a public exponent e such that $1<e<ϕ(n)$ and $gcd(e,ϕ(n))=1$.
    - She computes the private exponent d such that ed≡1(modϕ(n)). This $d$ acts as the multiplicative inverse of $e$ within $Z_{ϕ(n)}^{*}$​. This implies that there is a $k$ for which $ed=1+kϕ(n)$.
    - She publishes the pair $(n,e)$ as his public key and keeps $d$ as his private key.
2. **Encryption (by Bob):** Bob converts his message into an integer m such that 0≤m<n. He then computes the ciphertext c as $c≡m^{e}\pmod{n}$.
    
3. **Decryption (by Alice):** Alice decrypts the ciphertext c by computing $m≡m^{e}\pmod{n}$. The bijection property discussed earlier guarantees correct decryption: since ed≡1(modϕ(n)), ed=1+kϕ(n) and we know cd≡(me)d≡med≡m1+kϕ(n)≡m(modn), so Alice recovers the original message m.
    

In practice, m is typically limited to 2048 bits or more to avoid certain types of attacks, since there is no longer a bijection to arbitrarily large m.

**Deterministic Encryption and its Implications:**

RSA encryption is deterministic. This means that encrypting the same message always produces the same ciphertext. This can be a vulnerability if the message space is small (e.g., “yes” or “no”). An attacker could potentially encrypt all possible messages with the public key and compare the results to the intercepted ciphertext, effectively decrypting the message. Therefore, in practice, padding schemes are used to introduce randomness and prevent such attacks.

