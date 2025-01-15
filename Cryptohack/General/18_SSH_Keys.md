# SSH Keys (35 pts)
crypto

## Deskripsi
> Extract the modulus n as a decimal integer from [Bruce's SSH public key](https://cryptohack.org/static/challenges/bruce_rsa_6e7ecd53b443a97013397b1a1ea30e14.pub).

## Solusi
Diberikan file SSH public key milik bruce, kita diminta mengekstrak nilai modulus n dari file tersebut.
pertama, ubah format file menjadi PEM

``` bash
ssh-keygen -f bruce_rsa.pub -e -m pem > bruce_rsa.pem
```
kemudian seperti challenge sebelumnya, kita dapat mengambil nilai modulus n dari file PEM dengan menggunakan script python

``` python
from Crypto.PublicKey import RSA

f = open('bruce_rsa.pem', 'r')
key = RSA.import_key(f.read())

print(key.n)
```
