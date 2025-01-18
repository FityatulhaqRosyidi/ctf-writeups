# Marin's Secrets (50 pts)
crypto

## Deskripsi
> I've found a super fast way to generate primes from my secret list.

## Solusi
Diberikan n, e, dan ct. Kita diminta untuk mendekripsi ct. 
perhatikan bahwa p dan q yang dihasilkan adalah bilanhgan prima berbentuk $2^k-1$. 
bilangan-bilangan ini disebut dengan [Mersenne Prime](https://en.wikipedia.org/wiki/Mersenne_prime).

ukuran n adalah 4484 bit. jadi, faktor-faktornya pasti berukuran dibawah 4484.

pertama-tama, cek dulu semua mersenne primes dibawah 4484 bit
``` python
from Crypto.Util.number import isPrime

secrets = []
for i in range(4484):
    p = 2**i - 1
    if isPrime(p):
        secrets.append(i)
print(secrets)
```
dihasilkan list seperti berikut
``` console
[2, 3, 5, 7, 13, 17, 19, 31, 61, 89, 107, 127, 521, 607, 1279, 2203, 2281, 3217, 4253, 4423]
```
tentukan m, n dimana

$$ 2^m2^n \le 2^{4484} $$
$$ m + n \le 4484 $$

2 bilangan yang cocok adalah `2203` dan `2281`. Jadi,
``` console
p = 2**2203 - 1
q = 2**2281 - 1
```

Lanjutkan dengan [Known pq Attack](../../Attack_Templates/RSA_Known_pq_Attack.md)
