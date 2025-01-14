# You either know, XOR you don't (30 pts)
crypto

## Deskripsi
> I've encrypted the flag with my secret key, you'll never be able to guess it.
> ``` console
> 0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104
> ```

## Solusi
diberikan sebuah hex string, kita diminta mencari key yang dapat men decrypt hex tersebut. 
panjang key tidak diketahui. 

pada ppersoalan ini, kita dapat melakukan konsep crypto attack bernama known-plaintext attack.
kita mengetahui pasti format plaintext yaitu ```crypto{___}```. karena xor adalah operasi yang komutatif,
maka kita lakukan xor antara ciphertext dengan expected plaintext yang diketahui

``` python
from pwn import xor

ct = bytes.fromhex("0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104")
key = xor(ct, 'crypto{')
print(key)
```
akan didapat hasil
``` console
b'myXORke+y_Q\x0bHOMe$~seG8bGURN\x04DFWg)a|\x1dTM!an\x7f'
```
karena panjang expected plaintext kita hanya 7, kita ambil 7 karakter awal dari hasil diatas yaitu ```myXORke```.
secara intuisi, key yang valid mungkin adalah ```myXORkey```.

jika kita eksekusi dengan menggunakan key  ```myXORkey```, didapat hasil

``` console
b'crypto{1f_y0u_Kn0w_En0uGH_y0u_Kn0w_1t_4ll}'
```



