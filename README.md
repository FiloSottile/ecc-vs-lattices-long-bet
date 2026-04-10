# Long Bet Agreement

*ML-KEM-768 vs. X25519*

This agreement is between **Matthew Green** ("Lattice Cryptanalysis side") and **Filippo Valsorda** ("Quantum Computers side").

It is motivated by views about the security and deployment relevance of the X25519MLKEM768 hybrid handshake. Notwithstanding that motivation, this agreement is not a bet on any hybrid handshake, combiner, or protocol composition. The covered constructions are the separate underlying components defined in Section 1.

**Deadline.** December 31, ______, 23:59:59 UTC.

**Stakes.**

- Main wager: USD $5,000.
- Secondary wager: USD $1,000.
- Moral win: Filippo Valsorda buys Matthew Green drinks if Section 4 is satisfied.

## 1. Definitions

**ML-KEM-768** means the ML-KEM-768 parameter set as standardized in FIPS 203, used with conforming key generation, encapsulation, and decapsulation on honestly generated inputs.

**ML-KEM-512** means the ML-KEM-512 parameter set as standardized in FIPS 203, used with conforming key generation, encapsulation, and decapsulation on honestly generated inputs. It is used only for the moral win in Section 4.

**X25519** means X25519 as specified in RFC 7748, used for Diffie–Hellman on honestly generated public keys derived from properly clamped scalars.

## 2. Main wager: which breaks first

The main wager is resolved only by a practical break of one of the covered constructions.

### 2a. What counts as a break.

A covered construction is deemed broken if, by the deadline, a practical classical or quantum attack — executed on a real physical machine existing by the deadline — credibly demonstrates any of:

*For ML-KEM-768:*

- recovery of the shared secret from a public key and ciphertext without access to the decapsulation key;
- recovery of the decapsulation key from the encapsulation key; or
- an equivalent capability that allows decryption of ciphertexts.

*For X25519:*

- recovery of the shared secret from public keys without access to either party's private scalar;
- recovery of a party's private scalar from its public key; or
- an equivalent capability that allows computation of shared secrets.

### 2b. Winner.

- If only ML-KEM-768 is broken by the deadline, Matt wins.
- If only X25519 is broken by the deadline, Filippo wins.
- If both are broken, the party whose adverse event occurred first wins. If they cannot reasonably be ordered, the wager is a push and no payment is owed.
- If neither is broken, the main wager is a push and no payment is owed.

## 3. Secondary wager: material downgrade

The secondary wager captures a substantial, academically recognized downgrade short of a full practical break. Unlike the main wager, it is timeline-based.

### 3a. ML-KEM-768 falls below 128-bit security → Matt wins $1,000.

ML-KEM-768 is deemed materially downgraded if, by the deadline, either NIST states in substance that ML-KEM-768 no longer meets the 128-bit security level, or a majority of the arbiters concludes — based on peer-reviewed or clearly substantiated public cryptanalysis — that the academic consensus is that ML-KEM-768 no longer meets the 128-bit security level.

### 3b. ML-KEM-768 falls below 192-bit but stays at or above 128-bit security → draw.

If, by the deadline, ML-KEM-768 is no longer considered to meet the 192-bit security level but still meets the 128-bit security level (by the same criteria as 3a), the secondary wager is a push and no payment is owed.

### 3c. ML-KEM-768 stays at or above 192-bit security → Filippo wins $1,000.

If ML-KEM-768 is *not* deemed to have fallen below the 192-bit security level by the deadline, Filippo wins the secondary wager.

## 4. Moral win: ML-KEM-512

Separate from the main and secondary wagers, Filippo Valsorda owes Matthew Green a reasonable round of drinks if, by the deadline, ML-KEM-512 is no longer considered secure for new deployments.

ML-KEM-512 shall be treated as no longer secure if, by the deadline, either:

- NIST states in substance that ML-KEM-512 no longer meets the 120-bit security level; or
- a majority of the arbiters concludes — based on peer-reviewed or clearly substantiated public cryptanalysis — that the academic consensus is that ML-KEM-512 no longer meets the 120-bit security level.

This is honorary only and creates no monetary obligation beyond buying drinks.

## 5. Exclusions

The following do not count toward any wager:

- Side channels, timing leaks, cache attacks, power analysis, fault injection, or similar implementation-dependent techniques.
- RNG failures, biased or malformed key generation, protocol misuse, downgrade attacks, or implementation bugs.
- Attacks that rely only on malformed or nonconforming inputs outside the primitive's standardized, honestly generated use.
- Purely asymptotic, conjectural, or resource-estimate-only results without a real machine demonstration (main wager only).
- Generic recommendations to migrate to post-quantum or hybrid key establishment, absent a substantive security downgrade of ML-KEM-768 itself.
- Political, procurement, or ecosystem preferences unconnected to substantive security concerns.
- Any case in which the key could have credibly been compromised through algorithm-independent mechanisms.

## 6. Arbiters and evidence

**Arbiters.** Three arbiters: one selected by Matthew Green, one by Filippo Valsorda, one jointly selected by both parties. Questions of interpretation and sufficiency of proof are resolved by majority vote.

**Evidence.** A claimed adverse event may be established by a public result that the arbiters accept, or by a challenge procedure approved by the arbiters.

## 7. Miscellaneous

This document may be signed in counterparts. The parties may amend this agreement only in a later writing signed by both parties. All dollar amounts are in U.S. dollars.

## Signatures

[ Not signed yet ]
