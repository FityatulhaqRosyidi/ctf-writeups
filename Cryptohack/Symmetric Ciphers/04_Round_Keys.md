# Round Keys (20 pts)
crypto

## Deskripsi
> Complete the ```add_round_key``` function, then use the ```matrix2bytes``` function to get your next flag.
>
> chall : [add_round_key.py](https://cryptohack.org/static/challenges/add_round_key_b67b9a529ae739156107a74b14adde98.py)

## Solusi
Kita diminta untuk menyempurnakan fungsi ```add_round_key``` yang digunakan untuk men-xor setiap byte blok key dengan blok state
``` python
from pwn import xor

def add_round_key(s, k):
    return xor(s, k)
```
