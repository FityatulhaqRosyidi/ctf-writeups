faktorisasi $N$ jika selisih $p$ dan $q$ kecil

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

p, q = fermat(n)
```

further reading:
- [Fermat Factorization](https://facthacks.cr.yp.to/fermat.html)
