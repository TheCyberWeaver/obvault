Lecture from: 11.11.2024 | Video: [Videos ETHZ](https://video.ethz.ch/lectures/d-infk/2024/autumn/252-0025-01L/3667ceb4-0972-4855-bf3a-4a9642561067.html)

Last time, we explored the isomorphism between and . A key strategy for demonstrating such isomorphisms is to examine the orders of elements and, in particular, to find generators for each group.

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113151506.png)

Recall that . We found that:

**In :**

- 3 has order 4.
- -1 (or 19) has order 2. **In :**
- (0,1) has order 4.
- (1,0) has order 2.
- (1,2) has order 2.

By matching elements of the same order, we can construct a mapping between the two groups. As shown in the image, we mapped 3 to (0,1) and -1 to (1,0). This partial mapping helps to determine the full isomorphism. Once generators are mapped, the rest of the mapping follows from the homomorphism property.

This establishes an isomorphism because it defines a bijective homomorphism.

- **Homomorphism:** The mapping preserves the group operation. That is, if we map two elements from to and then perform the operation in , we get the same result as if we performed the operation in and then mapped the result. This needs to be verified for the chosen generators.
- **Bijective:** The mapping is one-to-one and onto. Every element in maps to a unique element in , and every element in has a pre-image in .

Because the mapping is a bijective homomorphism, it’s an isomorphism, demonstrating that the two groups have the same underlying structure despite their different representations. The existence of an isomorphism is typically not trivial to prove; there’s no general algorithmic approach. However, by examining element orders, and especially generators and their relations, we can often simplify the process of finding an isomorphism.

## Powers

Let be a group. We define integer powers of an element as follows:

- : The zeroth power of any element is the identity element.
- **( times)** for : The -th power is the element combined with itself times using the group operation.
- : The negative first power is the inverse of .
- for : The negative -th power is the -th power of the inverse of . With these definitions, the following properties hold for all integers and :

These properties establish a homomorphism from the additive group of integers to the group . Consider the map defined by for a fixed element . Then:

This shows that is a homomorphism. This homomorphism maps the additive structure of integers to the multiplicative structure (repeated application of the group operation) within . Note that this may not always be an isomorphism, as may not cover all of , nor is necessarily unique. However, if the homomorphism is surjective (meaning covers all of ), then is a cyclic group with as the generator.

## Order of an Element

The **order of an element** in a group is the smallest positive integer such that . If no such positive integer exists, the order of is said to be infinite.

Intuitively, the order of an element represents how many times the element needs to be combined with itself using the group operation to reach the identity element.

**Examples:**

- **In (additive group):** The order of 1 is 4, because , and 4 is the smallest positive integer with this property. The order of 2 is 2, because .
    
- **In (additive group):** The order of any non-zero integer is infinite, because no matter how many times we add a non-zero integer to itself, we will never reach 0.
    
- **In (multiplicative group):** The order of 2 is 4, because , , , and .
    

**Note on Terminology:**

The term “order” is unfortunately used in two different contexts in group theory:

1. **Order of a group:** This refers to the cardinality (number of elements) of the group, often denoted as .
2. **Order of an element:** This refers to the smallest positive integer power that results in the identity element.

The context usually makes it clear which meaning is intended.

### Finite Groups imply finite order for any element

**Theorem:** In a finite group , every element has finite order.

**Proof:**

Consider the powers of : . Since is finite, there must be a repetition among these powers. That is, there exist integers and with such that .

Multiplying both sides of this equation by (which exists since is a group), we get:

Since , is a positive integer. Therefore, we have found a positive integer such that . This means that the order of is finite and at most .

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113160627.png)

### Generators of a Group

A **generator** of a group is an element such that every element of can be expressed as a power of (using the group operation). In other words, for every , there exists an integer such that .

A group that has a generator is called a **cyclic group**. Cyclic groups are denoted by , where is the generator.

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113162707.png)

**Examples:**

- : The group of integers modulo 4 under addition is cyclic. The element 1 is a generator, since every element can be expressed as a multiple of 1: (using additive notation, this means ), , (), (). 3 is also a generator.
    
- : More generally, the group of integers modulo under addition is always cyclic. The element 1 is a generator. Other elements can be generators too, specifically those coprime to .
    
- : The Klein four-group is not cyclic. No single element can generate all other elements. Every element other than the identity has order 2.
    
- : The symmetric group on 3 elements is not cyclic. There is no single permutation that can generate all other permutations.
    

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113161115.png)

**Properties of Cyclic Groups:**

- **Abelian:** All cyclic groups are abelian (commutative). This follows directly from the definition and the properties of powers: .
    
- **Order of a Cyclic Group:** The order of a cyclic group is the smallest positive integer such that , where is the generator.
    
- **Subgroups:** All subgroups of a cyclic group are also cyclic.
    
- **Isomorphic to or :** Every cyclic group is isomorphic to either (if the group is finite of order ) or to (if the group is infinite).
    

## Lagrange’s Theorem

Let be a finite group and be a subgroup of . Then the order of divides the order of . That is, is a divisor of .

**Proof:**

The proof relies on the concept of **cosets**. A left coset of in is a set of the form for some . Similarly, a right coset is . We will focus on left cosets, but the argument is analogous for right cosets.

1. **Cosets partition G:** The left cosets of partition . This means that every element of belongs to exactly one left coset of . To see this:
    
    - Every element belongs to the coset (since and ).
    - If two cosets and intersect (i.e., have a common element), then they are equal. Suppose for some . Then . Since is a subgroup, . Let . Then , and therefore . Thus if two left cosets intersect they are equal.
2. **All cosets have the same size:** Every left coset has the same cardinality as . This can be shown by defining a bijection by . This function is clearly surjective, and it’s injective because if , then by the cancellation law in .
    
3. **Order of G is the sum of coset sizes:** Since the cosets partition and all have size , the order of is the number of cosets multiplied by the size of each coset. Let be the number of distinct left cosets of in . Then .
    

Therefore, divides .

### Consequences of Lagrange’s Theorem

Lagrange’s Theorem, which states that the order of any subgroup of a finite group divides the order of the group, has several important implications:

- **Order of Elements:** The order of any element in a finite group divides the order of the group (). This is because the set of powers of forms a cyclic subgroup of , and the order of this subgroup is equal to the order of .
    
- **Groups of Prime Order:** A group of prime order has no nontrivial proper subgroups. This follows directly from Lagrange’s Theorem. Any subgroup must have an order that divides , so the only possible subgroup orders are 1 and . The subgroup of order 1 is the trivial subgroup, and the subgroup of order is the group itself. Consequently, a group of prime order must be cyclic and therefore has a generator. Any element other than the identity will generate the entire group.
    

**Further Consequences:**

- : This follows directly from the definition of the order of an element. The order of is the smallest positive integer such that .
    
- : Since divides , we can write for some integer . Then, . This result is sometimes referred to as Euler’s theorem when applied to modular arithmetic.
    

## Multiplicative Groups Modulo _m_

The set , consisting of the integers modulo that are coprime to , forms a group under multiplication modulo . This group is denoted as .

**Proof that is closed under** :

We need to show that if and are in , then their product (which is equivalent to ) is also in . In other words, if and , then .

This follows from the fundamental theorem of arithmetic. If , then and share no common prime factors. Similarly, if , then and share no common prime factors. The prime factorization of is simply the combination of the prime factors of and . Since neither nor shares any prime factors with , their product also shares no prime factors with . Therefore, , and belongs to . This demonstrates closure.

The other group axioms (associativity, identity, and inverses) also hold for .

### Euler’s Totient Function

Euler’s totient function, denoted by , counts the number of positive integers less than or equal to that are coprime to . In other words, is the size of the set .

#### Formal Definition

#### Properties of

- **For a prime** : . Since is prime, all integers less than are coprime to it.
- **For a prime power** : . The integers not coprime to are multiples of : . There are such multiples.
- **Multiplicativity:** If , then . This means that is a multiplicative function.
- **Formula using prime factorization:** If is the prime factorization of , then: where the product is taken over the distinct prime factors of .

#### Example

- . The numbers coprime to 10 are 1, 3, 7, and 9.
- . The numbers coprime to 12 are 1, 5, 7, and 11.


### Consequence

As a consequence of Lagrange’s theorem and the fact that , for any element , we have:

This is known as **Euler’s theorem**.

**Explanation:**

1. **is a group of order :** Euler’s totient function counts the number of elements in , which are the integers less than or equal to that are coprime to .
    
2. **Lagrange’s theorem:** The order of any element in a finite group divides the order of the group. In our case, the order of any element must divide .
    
3. **Raising to the power of the group’s order:** As we saw earlier as a consequence of Lagrange’s theorem, raising any element to the power of the group’s order results in the identity element. In , the group operation is multiplication modulo , and the identity element is 1. Therefore, for any :
    

This is Euler’s theorem. It’s a generalization of Fermat’s Little Theorem, which applies specifically to the case where is a prime number. If , where is prime then , , and thus Euler’s theorem says for , which is Fermat’s Little Theorem.

### Bijections in Groups and Exponentiation

A crucial concept in understanding group structure and its applications, especially in cryptography, is the idea of bijections induced by exponentiation. Under certain conditions, raising elements of a group to a specific power can create a one-to-one and onto mapping from the group to itself.

**Theorem:** Let be a finite group of order , and let be an integer such that . Then the map defined by is a bijection.

**Proof:**

The core of the proof lies in demonstrating the existence of an inverse map. Since , there exists an integer such that . This means there is an integer where:

We will show that the map defined by is the inverse of . Consider the composition of and :

Using the equation , we can rewrite the exponent:

By a consequence of Lagrange’s theorem, we know that for any element in a finite group , (the identity element). Therefore:

Thus, , meaning is the inverse of . The existence of an inverse map proves that is a bijection.

**Significance in Cryptography (RSA):**

This theorem has direct applications in the RSA cryptosystem. In RSA, we work with the multiplicative group , where is the product of two large primes. The order of this group is .

- is chosen such that , and becomes the public key.
- is the inverse of modulo , satisfying . The value is kept as the private key.

Encryption involves raising the message (represented as a number ) to the power of modulo : . Decryption involves raising the ciphertext to the power of modulo : . The bijection property ensures that these operations are inverses of each other, allowing the original message to be recovered. This is based on the fact, proven above, that since . Thus .

Therefore, the concept of bijections induced by exponentiation is fundamental to the security and functionality of the RSA cryptosystem.

## RSA (Public Key Encryption)

RSA is a widely used public-key cryptosystem that relies on the mathematical properties of modular arithmetic and prime numbers. It enables secure communication over insecure channels, allowing for both encryption and digital signatures.

**Public-Key Cryptosystems:**

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113180952.png)

In a public-key cryptosystem, each participant has a pair of keys: a public key ( for Bob) and a private key ( for Bob). The public key can be freely distributed, while the private key must be kept secret. Anyone can encrypt a message using the recipient’s public key, but only the recipient, possessing the corresponding private key, can decrypt the message. **Crucially, while the channel itself may be insecure, an authentic channel for distributing public keys is essential for the security of the system.** If an adversary can tamper with the public key distribution, they can substitute their own public key, allowing them to intercept and decrypt messages intended for the original recipient.

**Mechanical Analogy:**

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113180945.png)

A mechanical analog for a public-key system is a lockbox with a slot. Anyone can place a message in the slot and close the lock (encrypt), but only the person with the key can open the lock and retrieve the message (decrypt).

**RSA Algorithm:**

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113181052.png)

The RSA algorithm involves the following steps:

1. **Key Generation:**
    
    - Alice generates two large prime numbers, and .
    - She computes and .
    - Alice selects a public exponent such that and .
    - She computes the private exponent such that . This acts as the multiplicative inverse of within . This implies that there is a for which .
    - She publishes the pair as his public key and keeps as his private key.
2. **Encryption (by Bob):** Bob converts his message into an integer such that . He then computes the ciphertext as .
    
3. **Decryption (by Alice):** Alice decrypts the ciphertext by computing . The bijection property discussed earlier guarantees correct decryption: since , and we know , so Alice recovers the original message .
    

In practice, is typically limited to 2048 bits or more to avoid certain types of attacks, since there is no longer a bijection to arbitrarily large m.

**Deterministic Encryption and its Implications:**

RSA encryption is deterministic. This means that encrypting the same message always produces the same ciphertext. This can be a vulnerability if the message space is small (e.g., “yes” or “no”). An attacker could potentially encrypt all possible messages with the public key and compare the results to the intercepted ciphertext, effectively decrypting the message. Therefore, in practice, padding schemes are used to introduce randomness and prevent such attacks.

**Digital Signatures:**

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113181500.png)

Digital signatures provide a way to verify the authenticity and integrity of a message. Unlike encryption, which protects the confidentiality of a message, digital signatures ensure that a message has not been tampered with and originated from the claimed sender.

![](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/attachments/Pasted-image-20241113181650.png)

RSA can also be used for digital signatures. The process is similar to encryption, but the roles of the keys are reversed. The sender signs the message using their private key, and anyone can verify the signature using the sender’s public key and a known hash function . This verifies both authenticity of message and its origin.

**Continue here:** [17 Rings, Polynomial Rings, Integral Domains, Units](https://cs.shivi.io/01-Semesters-\(BSc\)/Semester-1/Discrete-Maths/Lecture-Notes/17-Rings,-Polynomial-Rings,-Integral-Domains,-Units)