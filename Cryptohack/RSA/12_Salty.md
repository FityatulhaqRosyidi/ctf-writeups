# Salty (20 pts)
crypto

## Deskripsi
> Smallest exponent should be fastest, right?
>
> Challenge:
> - [salty.py](https://cryptohack.org/static/challenges/salty_9854bdcadc3f8b8f58008a24d392c1bf.py)
> - [output.txt](https://cryptohack.org/static/challenges/output_95f558e889cc66920c24a961f1fb8181.txt)

## Solusi
diberikan nilai n, e, ct, dan sebuah script. celah serangan disini ada di nilai ```e = 1```.
Jika ```e = 1```, maka persamaan enkripsi akan menjadi :

$$ ct = m \bmod n $$

Perhatikan bahwa ukuran n dan ct berbeda jauh. n berukuran 1024 bits sedangkan ct 255 bits. Dan pada beberapa chall, nilai m tidak lebih dari 1024 bits. Jadi, operasi modulo dapat kita hilangkan sehingga didapat ```ct = m```.

``` python
# solver.py
from Crypto.Util.number import long_to_bytes

ct = 44981230718212183604274785925793145442655465025264554046028251311164494127485
decrypted = long_to_bytes(ct).decode()
print(decrypted)
```
