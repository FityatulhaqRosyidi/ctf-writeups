# Modular Arithmetic 1 (20 pts)
crypto

## Deskripsi
> Calculate the following integers:
> 
> $$ 11 \equiv x \bmod 6 $$
> $$ 8146798528947 \equiv y \bmod 17 $$
> 
> The solution is the smaller of the two integers, $(x,y)$, you obtained after reducing by the modulus.

## Solusi
Diberikan dua persamaan

$$ 11 \equiv x \bmod 6 $$
$$ 8146798528947 \equiv y \bmod 17 $$

diminta mencari nilai terkecil dari x dan y
``` python
print(min(11 % 6, 8146798528947 % 17))
```
hasilnya adalah ```4```

