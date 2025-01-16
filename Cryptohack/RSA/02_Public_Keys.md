# Public Keys (15 pts)
crypto

## Deskripsi
> "Encrypt" the number 12 using the exponent e=65537 and the primes p=17 and q=23. What number do you get as the ciphertext?

## solusi
gunakan script python untuk persoalan ini
``` python
m = 12
e = 0x10001 #65537
p = 17
q = 23
ct = pow(m, e, p*q)
print(ct)
```
