# Confusion through Substitution (25 pts)
crypto

## Deskripsi
> Implement ```sub_bytes```, send the state matrix through the inverse S-box and then convert it to bytes to get the flag.
>
> [chall.py](https://cryptohack.org/static/challenges/sbox_8fc04ffb95faf5a5e6959195d5e2d94e.py)

## Solusi
Kita diminta untuk melengkapi fungsi ```sub_bytes``` dari script challenge yang diberikan
``` python
def sub_bytes(s, sbox=s_box):
    return list(map(lambda x: sbox[x], sum(s, [])))

print(bytes(sub_bytes(state, sbox=inv_s_box)))
```

