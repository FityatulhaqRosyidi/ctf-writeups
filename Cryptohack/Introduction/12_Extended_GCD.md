# Extended GCD (20 pts)
crypto

## Deskripsi
> Using the two primes ```p=26513```,```q=32321```, find the integers ```u,v``` such that
>
> $$p \cdot u + q \cdot v = \gcd(p, q)$$


## Solusi
diberikan nilai p dan q, kita diminta mencari nilai u dan v yang memenuhi persamaan :

$$p \cdot u + q \cdot v = \gcd(p, q)$$

kita dapat menemukan u dan v dengan menggunakan algoritma extended euclidian

``` python
def egcd(a, b):
    if a == 0:
        return b, 0, 1
    else:
        gcd, x, y = egcd(b % a, a)
        return gcd, y - (b // a) * x, x

gcd, u, v, = egcd(26513, 32321)
print(min(u, v))
```

hasilnya adalah ```-8404```
