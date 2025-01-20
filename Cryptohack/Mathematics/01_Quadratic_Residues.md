# Quadratic Residues (25 pts)
crypto

## Deskripsi
> In the below list there are two non-quadratic residues and one quadratic residue.
>
> Find the quadratic residue and then calculate its square root. Of the two possible roots, submit the smaller one as the flag.
>
> $$  p=29 \ \ \ \ ints=[14,6,11] $$

## Solusi
`Quadratic Residue` adalah bilangan anggota elemen modulus $p$ / elemen field $p$ yang bisa dicari akar kuadratnya.

maksudnya, $x$ disebut Quadratic Residue jika ada nilai $a$ yang memenuhi

$$ a^2 \equiv x \bmod p $$

Challenge diatas bisa diselesaikan dengan brute force. Iterasi $a$ dari $1$ sampai $p - 1$,  jika ada yang memenuhi, maka $x$ Quadratic Residue. Lalu cetak $a$ terkecil.
``` python
p = 29
ints = [14, 6, 11]

res = []
for x in ints:
    for a in range(1, p):
        if (pow(a, 2, p) == x):
            res.append(a)

print(min(res))
```
