# Hex (5 pts)
Crypto

## Deskripsi 
> When we encrypt something the resulting ciphertext commonly has bytes which are not printable ASCII characters. If we want to share our encrypted data, it's common to encode it into something more user-friendly and portable across different systems.
>
> Hexadecimal can be used in such a way to represent ASCII strings. First each letter is converted to an ordinal number according to the ASCII table (as in the previous challenge). Then the decimal numbers are converted to base-16 numbers, otherwise known as hexadecimal. The numbers can be combined together, into one long hex string.
>
> Included below is a flag encoded as a hex string. Decode this back into bytes to get the flag.
> ``` console 
> 63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d
> ```

## Solusi
Kita diberi string hex yg panjang untuk didecrypt. 
untuk mengonversi string hex ke bytes di python, kita dapat menggunakan fungsi ```bytes.fromhex()```

penjelasan hexadecimal dapat dilihat [disini](https://en.wikipedia.org/wiki/Hexadecimal)

``` python
ct = "63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d"
print(bytes.fromhex(ct))
```


