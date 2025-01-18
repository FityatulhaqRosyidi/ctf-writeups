Gunakan untuk mendekripsi ct jika $p$ dan $q$ diketahui

``` python
from Crypto.Util.number import long_to_bytes,inverse

# p = 
# q = 
# e = 0x10001
# ct =

n = p*q
phi = (p-1) * (q-1)
d = inverse(e, phi)
m = pow(ct, d, n)

print(long_to_bytes(m))
```
