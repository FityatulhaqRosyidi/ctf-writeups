# Round Keys (20 pts)
crypto

## Deskripsi
> Complete the ```add_round_key``` function, then use the ```matrix2bytes``` function to get your next flag.
>
> chall : [add_round_key.py](https://cryptohack.org/static/challenges/add_round_key_b67b9a529ae739156107a74b14adde98.py)

## Solusi
``` python
from pwn import xor

state = [
    [206, 243, 61, 34],
    [171, 11, 93, 31],
    [16, 200, 91, 108],
    [150, 3, 194, 51],
]

round_key = [
    [173, 129, 68, 82],
    [223, 100, 38, 109],
    [32, 189, 53, 8],
    [253, 48, 187, 78],
]

def add_round_key(s, k):
    return xor(s, k)

print(add_round_key(state, round_key))
```
