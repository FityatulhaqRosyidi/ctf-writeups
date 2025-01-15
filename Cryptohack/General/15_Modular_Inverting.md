# Modular Inverting (25)
crypto

## Deskripsi
> what is the inverse element
>
> $$ d = 3 ^{-1} $$
>
> such that
>
> $$ 3 \cdot d \equiv 1 \bmod 13 $$ 
> 

## Solusi
untuk mencari invers modular, kita dapat memanfaatkan fungsi ```inverse``` yang disediakan library ```pycryptodome```.

``` python
from Crypto.Util.number import inverse

print(inverse(3, 13))
```
hasilnya adalah ```9```

