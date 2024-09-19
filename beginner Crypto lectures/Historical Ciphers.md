## Caesar Cipher
shift cipher
example of modular arithmetic
mod 26
K=3 $a \rightarrow d$
 ...
 $x \rightarrow a$

and so on 

decryption goes the opposite

 weak break letter frequency analysis
 also trying all the 25 cases is easy
 incredibly weak
 so lets make it better

## Affine Cipher
$k=(a,b)$ where $gcd(a,26) = 1$
$e_k(x)=y\equiv a*x+b \mod 26$
$d_k(y)=x\equiv=a^{-1} *(y-b)\mod 26$
the gcd is important so we always have an multiplicative inverse #crings

keyspace is
$K=A*B$
312 keys its too little 
and letter frequency analysis still works too its pretty bad