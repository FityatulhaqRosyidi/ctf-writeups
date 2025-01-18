# Crossed Wires (100 pts)
crypto

## Deskripsi
> I asked my friends to encrypt our secret flag before sending it to me, but instead of using my key, they've all used their own! Can you help?
>
> Challenge:
> - [source.py](https://cryptohack.org/static/challenges/source_b3c3c786c649d363d27995545cf95dab.py)
> - [output.txt](https://cryptohack.org/static/challenges/output_434cbf2b937bac1177bed299b2049a92.txt)

## Solusi
Diberikan nilai N, d1, e1, e2, e3, e4, e4, e6, dan ct. kita diminta mendekripsi ct yang sudah di enkripsi dengan 5 public keys (e2 - e6).
Jadi, kita perlu mencari 5 private keys (d2 - d6). 

pertama - tama, faktorisasi N.
sumber [berikut](https://www.di-mgt.com.au/rsa_factorize_n.html) menjelaskan cara memperoleh faktor N jika diketahui e dan d.

diperoleh ```p=0xe5f0c56af9d879da10d5b7f09153716469faced27adf10a8c69847e2460767d316048b95087bf1102278ca070e2fb81ac367aae538980ad0cbd438ffac3673c9b8898a24209d896723a9b08e919a6cbfff761cb8218df0d1f6f56414ba245ad17581d96bca6679b3fa7a2a7d2306ad99c1749864cd85b3390aaddef33e8c73b9```
dan
```q=0xbf7a6a86c980cbc7ff358a92b7b0828106b6ad75122c42b9c05cfb0f1b08205903e54381a323b3c2dfc6a6adb0771dbdf61185405ec7e1de5614cdfa71c6b5cd320d0a6bc40379592088a794b0ead8cc012a38ca57daaed140c42c634736eee8fe268bac6ab814b1e769dc1bade805160da940b0813b145df9b7a97e7ca4e0eb```

kemudian setelah diperoleh faktor2 N, d2 - d6 bisa diperoleh dengan mudah.
```python
from Crypto.Util.number import long_to_bytes, inverse

# p, q, n, ct = REDACTED

friend_keys = [106979, 108533, 69557,  97117, 103231]

phi = (p-1) * (q-1)
for e in friend_keys:
    d = inverse(e, phi)
    ct = pow(ct, d, n)

print(long_to_bytes(ct).decode())

```
