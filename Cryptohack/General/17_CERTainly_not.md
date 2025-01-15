# CERTainly not (30 pts)
crypto

## Deskripsi
>  Presented here is a DER-encoded x509 RSA [certificate](https://cryptohack.org/static/challenges/2048b-rsa-example-cert_3220bd92e30015fe4fbeb84a755e7ca5.der). Find the modulus of the certificate, giving your answer as a decimal.

## Solusi
``` python
from Crypto.PublicKey import RSA

with open('privkey.der','rb') as f:
    key = RSA.import_key(f.read())

print(key.n)
```
