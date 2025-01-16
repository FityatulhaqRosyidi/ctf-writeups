# Favourite byte (20 pts)
crypto

## Deskripsi
> I've hidden some data using XOR with a single byte, but that byte is a secret. Don't forget to decode from hex first.
> ``` console
> 73626960647f6b206821204f21254f7d694f7624662065622127234f726927756d
> ```

## Solusi
diberikan sebuah hex, hasil dari xor antara flag dengan sebuah byte/karakter random. challenge ini cukup mudah karena kita hanya perlu mencari
satu buah byte random. cukup bruteforce tiap karakter ascii dari 0-200

``` python
from pwn import xor

ct = bytes.fromhex("73626960647f6b206821204f21254f7d694f7624662065622127234f726927756d")
for i in range(200):
    ct = xor(ct, i)
    if (ct[:6] == b'crypto'):
        print(ct)
```
