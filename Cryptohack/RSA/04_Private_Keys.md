# Private Keys (20 pts)
crypto

## Deskripsi
> Given the two primes:
>``` console
> p = 857504083339712752489993810777
> q = 1029224947942998075080348647219
>```
> and the exponent e = 65537. what is the private key d?

## Solusi
untuk mencari private key d, pertama-tama kita harus mencari nilai $\phi(N)$.

$$ \phi(N) = (p - 1)(q - 1) $$

setelah itu, d bisa dicari dengan invers modular

$$ d \equiv e^{-1} \bmod \phi(N) $$

solusi dengan script python :
``` python
from Crypto.Util.number import inverse

p = 857504083339712752489993810777
q = 1029224947942998075080348647219
e = 0x10001

phi = (p-1) * (q-1)
d = inverse(e, phi)
print(d)
```
