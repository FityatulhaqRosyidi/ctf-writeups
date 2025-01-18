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
oleh karena itu, gunakan teknik faktorisasi [fermat](https://facthacks.cr.yp.to/fermat.html) untuk mendapat $p$ dan $q$.
(Sebenarnya pake factordb juga kebetulan bisa sih)

``` python
from sympy.ntheory.primetest import is_square
from Crypto.Util.number import long_to_bytes,inverse
import sympy

def fermat(n):
    a = int(sympy.sqrt(n)) 
    b = (a*a) - n
    while not is_square(b):
        a += 1
        b = (a*a) - n
    else:
        p = int(a - (sympy.sqrt(b)))
        q = n//p
        if p * q == n:
            return p,q
        else:
            return "No Luck"

# n =
# e = 
# ct =

p, q = fermat(n)

phi = (p-1) * (q-1)
d = inverse(e, phi)
m = pow(ct, d, n)

print(long_to_bytes(m))
```
