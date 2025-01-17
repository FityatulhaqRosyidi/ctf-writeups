# Inferius Prime (30 pts)
crypto

## Deskripsi
> Here is my super-strong RSA implementation, because it's 1600 bits strong it should be unbreakable... at least I think so!
>
> Challenge files: <br>
> [inferius.py](https://cryptohack.org/static/challenges/inferius_2facb420dc30897696869e3fd11b4b4f.py)
> [output.txt](https://cryptohack.org/static/challenges/output_cf39018a5db981bd454ddcdcf6595167.txt)

## Solusi
Diberikan nilai n, e, dan ct. kita diminta untuk mendekripsi ct.
Challenge ini cukup mudah dan sederhana karena ukuran n relatif kecil.
cukup gunakan tools web factordb.com, kita bisa memperoleh faktor-faktor n (p dan q).

``` python
from Crypto.Util.number import getPrime, inverse, bytes_to_long, long_to_bytes, GCD

e = 0x10001
p = 848445505077945374527983649411
q = 1160939713152385063689030212503
ct = 948553474947320504624302879933619818331484350431616834086273
phi = (p - 1) * (q - 1)
d = inverse(e, phi)
n = p * q
pt = pow(ct, d, n)
decrypted = long_to_bytes(pt)
print(decrypted)
```

