2 main types async and sync, async uses the cyphertext as an additional input for the key stream generation
K- key 
A stream cipher encrypts bits individually i.e in a stream
$y_i=e(x_i)\equiv x_i+s_i\mod 2$
$x_i=d(y_I)\equiv x_i + s_i \mod 2$
mod 2 aka bits basically
mod 2 additon and subtraction is the same operation (yknow not bytes in this way nowhere to carry)
addition mod 2 is XOR (also why we use this cipher everywhere good ol ez hardware)
2xXOR with the key gives the original data
the output of a stream cipher is 50% at every time


The key stream is the important/hard thing
how do we generate the key stream so that the attacker doesn't know it
[[RNG]]
### TRNG
(OTP-One Time Pad) that both sides know, but the attacker doesn't
Unconditionally secure with infinite computing resources
def 1. use TRNG to generate it 2. do not reuse any key stream bits
needs a very key stream (Pad)- as big as the data - not realistic
useful in specific operation not in general computing
### PRNG - Linear Congruential gen
use a keystream from PRNG
LCG $S_0 = seed$
	$S_{i+1}=A*S_i+B\mod m$
	K =(A,B)
	Remark A, B,S
ATTACK:
Oscar knows x1,x2,x3 i.e a file header
 oscar also knows y
 y = x+s1
1) Oscar knows $S_1, S_2, S_3$
2) $S_2 \equiv A *S_1+B \mod m$
	$S_3 \equiv A *S_2+B \mod m$
	$A=(S_2-S_3)*(S_1-S_2)^{-1}$
this is why we need CSPRNG