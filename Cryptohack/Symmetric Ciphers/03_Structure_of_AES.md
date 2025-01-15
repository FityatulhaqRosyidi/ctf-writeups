# Structure of AES (15 pts)
crypto

## Deskripsi
> Included is a ```bytes2matrix``` function for converting our initial plaintext block into a state matrix.
> Write a ```matrix2bytes``` function to turn that matrix back into bytes, and submit the resulting plaintext as the flag.
>
> chall : [matrix.py](https://cryptohack.org/static/challenges/matrix_e1b463dddbee6d17959618cf370ff1a5.py)

## Solusi
Kita diminta membuat fungsi ```matrix2bytes``` yang mengubah blok karakter menjadi array karakter.
``` python
def matrix2bytes(matrix):
    return bytes(sum(matrix, []))
```
