3 types:
1. True (TRNG) (cosmic rays/ quantum effects /lavalamps/thermal noise, human mouse movement): truly random (as far as we know))
2. Pseudo (PRNG) (computable deterministic, only random from a human perspective, seeded randomness i.e minecraft, also base rand() functions in C ($s_0=12345$) and lots of other programming languages)
3. Cryptography Secure Pseudo (CSPRNG or CPRNG or CRNG)
   still pseudo random just much harder to guess; 
   an additional property: unpredictability
   informally given n output bits from $S_0$ its infeasible to construct $S_n$
   formally:
	   given n consecutive bits of the key stream, there is no polynomial time algorithm
	   that can predict the next bit s n+1 with better than 50% chance of success
