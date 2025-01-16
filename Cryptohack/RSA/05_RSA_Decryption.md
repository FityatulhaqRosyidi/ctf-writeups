# RSA Decryption (20 pts)
crypto

## Deskripsi
> I've encrypted a secret number for your eyes only using your public key parameters:
>```
> N = 882564595536224140639625987659416029426239230804614613279163
> e = 65537
>```
> Use the private key that you found for these parameters in the previous challenge to decrypt this ciphertext:
> ```
> c = 77578995801157823671636298847186723593814843845525223303932
> ```

## Solusi
Pertama, kita faktorkan N menjadi p dan q untuk mencari nilai d. karena nilai N lumayan
kecil, kita bisa menggunakan tools yang tersedia di web seperti factordb.com. 

dengan memiliki nilai p dan q, kita bisa memperoleh nilai d lalu mendecrypt ciphertext yang diberikan.

$$ plaintext = ciphertext^d \bmod N $$

``` python
from Crypto.Util.number import long_to_bytes, inverse

N = 882564595536224140639625987659416029426239230804614613279163
e = 0x10001
c = 77578995801157823671636298847186723593814843845525223303932
p = 857504083339712752489993810777
q = 1029224947942998075080348647219

phi = (p-1)*(q-1)
d = inverse(e, phi)
m = pow(c, d, N)
print(m)

```
