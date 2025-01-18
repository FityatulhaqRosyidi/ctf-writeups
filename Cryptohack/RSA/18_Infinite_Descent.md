# Infinite Descent (50 pts)
crypto

## Deskripsi
> Finding large primes is slow, so I've devised an optimisation.
>
> Challenge :
> - [descent.py](https://cryptohack.org/static/challenges/descent_240fda375202c97a3cbaf3fdedbb8266.py)
> - [output.txt](https://cryptohack.org/static/challenges/output_14f82a67efe7b7edffb810dbb7ab5f27.txt)

## Solusi
diberikan n, e, dan c. kita diminta untuk mendekripsi c.
perhatikan pada fungsi getPrimes, selisih $p$ dan $q$ yang dihasilkan tidaklah jauh.
oleh karena itu, gunakan teknik faktorisasi fermat untuk mendapat $p$ dan $q$.
(Sebenarnya pake factordb juga kebetulan bisa sih)

``` python
from Crypto.Util.number import long_to_bytes,inverse

# p = 
# q = 
# e = 
# ct =

n = p*q
phi = (p-1) * (q-1)
d = inverse(e, phi)
m = pow(ct, d, n)

print(long_to_bytes(m))
```
