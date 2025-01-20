Mengekstrak $n$ dan $e$ dari `public_key.pem`   
``` python
from Crypto.PublicKey import RSA

f = open('public_key.pem', 'r')
key = RSA.importKey(f.read())

n = key.n
e = key.e
```
