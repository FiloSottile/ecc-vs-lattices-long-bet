# The Hybrids Long Bet

*ML-KEM-768 vs. X25519*

This is a public wager between **Matthew Green** ("Lattice Cryptanalysis side") and **Filippo Valsorda** ("Quantum Computers side"). Stakes are settled by charitable donation (see Section 7).

It is motivated by views about the security and deployment relevance of the X25519MLKEM768 hybrid handshake. Notwithstanding that motivation, this wager is not about any hybrid handshake, combiner, or protocol composition. The covered constructions are the separate underlying components defined in Section 1.

🗞️ *As reported in [The Register](https://web.archive.org/web/20260410193326/https://www.theregister.com/2026/04/09/cryptograhpers_quantum_bet/).*

**Deadline.** December 31, 2040, 23:59:59 UTC.

**Stakes.**

- Main wager: what breaks first, ML-KEM-768 or X25519? → **USD $5,000 donation.**
- Secondary wager: will ML-KEM-768 weaken significantly? → **USD $1,000 donation.**
- Moral win: Filippo Valsorda buys Matthew Green drinks if ML-KEM-512 weakens.

**Back bets.**

Anyone can join the bet by choosing a side and stakes for the main and/or secondary wager.
If the selected side loses, the back bettor donates the staked amount to the charity chosen by the winner.
Back bettors don't select arbiters or charities, but can choose different dollar amounts.

- David Adrian: Quantum Computers side / **$10,000** on main wager / **$2,000** on secondary wager

- sanketh: Lattice Cryptanalysis side / **$1,000** on main wager / **$200** on secondary wager

> [!TIP]
> Do you have an _opinion_ and want to put your money where your mouth is?
> Do you like raising money for charity through abstruse wagers?
> Submit a PR and add your name above!

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
- If both are broken, the party whose adverse event occurred first wins. If they cannot reasonably be ordered, the wager is a push and no donation is made.
- If neither is broken, the main wager is a push and no donation is made.

## 3. Secondary wager: material downgrade

The secondary wager captures a substantial, academically recognized downgrade short of a full practical break. Unlike the main wager, it is timeline-based.

### 3a. ML-KEM-768 falls below 128-bit security → Matt wins, Filippo donates $1,000.

ML-KEM-768 is deemed materially downgraded if, by the deadline, either NIST states in substance that ML-KEM-768 no longer meets the 128-bit security level, or a majority of the arbiters concludes — based on peer-reviewed or clearly substantiated public cryptanalysis — that the academic consensus is that ML-KEM-768 no longer meets the 128-bit security level.

### 3b. ML-KEM-768 falls below 192-bit but stays at or above 128-bit security → draw.

If, by the deadline, ML-KEM-768 is no longer considered to meet the 192-bit security level but still meets the 128-bit security level (by the same criteria as 3a), the secondary wager is a push and no donation is made.

### 3c. ML-KEM-768 stays at or above 192-bit security → Filippo wins, Matt donates $1,000.

If ML-KEM-768 is *not* deemed to have fallen below the 192-bit security level by the deadline, Filippo wins the secondary wager.

## 4. Moral win: ML-KEM-512

Separate from the main and secondary wagers, Filippo Valsorda buys Matthew Green a reasonable round of drinks if, by the deadline, ML-KEM-512 is no longer considered secure for new deployments.

ML-KEM-512 shall be treated as no longer secure if, by the deadline, either:

- NIST states in substance that ML-KEM-512 no longer meets the 120-bit security level; or
- a majority of the arbiters concludes — based on peer-reviewed or clearly substantiated public cryptanalysis — that the academic consensus is that ML-KEM-512 no longer meets the 120-bit security level.

This is honorary only and carries no monetary stakes beyond buying drinks.

## 5. Exclusions

The following do not count toward any wager:

- Side channels, timing leaks, cache attacks, power analysis, fault injection, or similar implementation-dependent techniques.
- RNG failures, biased or malformed key generation, protocol misuse, downgrade attacks, or implementation bugs.
- Attacks that rely only on malformed or nonconforming inputs outside the primitive's standardized, honestly generated use.
- Purely asymptotic, conjectural, or resource-estimate-only results without a real machine demonstration (main wager only).
- Generic recommendations to migrate to post-quantum or hybrid key establishment, absent a substantive security downgrade of ML-KEM-768 itself.
- Political, procurement, or ecosystem preferences unconnected to substantive security concerns.
- Any case in which the key could have credibly been compromised through algorithm-independent mechanisms.
- Changes in overall security targets, such as NIST choosing to only recommend 256-bit primitives.
- When calculating security levels, any attacks that require hardware that does not exist at that time, such as quantum algorithms before they are demonstrated on real hardware.

## 6. Arbiters and evidence

**Arbiters.** Three arbiters: one selected by Matthew Green, one by Filippo Valsorda, one jointly selected by both parties. Questions of interpretation and sufficiency of proof are resolved by majority vote.

1. Sophie Schmieg, selected by Filippo Valsorda.
2. Madars Virza, selected by Matthew Green.
3. Thomas H. Ptacek, selected jointly.

**Evidence.** A claimed adverse event may be established by a public result that the arbiters accept, or by a challenge procedure approved by the arbiters.

## 7. Payment

All monetary wagers are settled by charitable donation. The losing party donates the amount to a U.S. 501(c)(3) organization chosen by the winning party at the time of payout.

Provisional designations:

- If Matt wins: Electronic Frontier Foundation (EFF).
- If Filippo wins: Internet Archive.

The winning party may substitute a different 501(c)(3) at the time of payout.

## 8. Miscellaneous

The parties may amend this wager by approving a PR. Adjudications and donations will be announced as edits.

All dollar amounts are in U.S. dollars.

This is a friendly honor-based wager, and not a legally-enforceable agreement.
