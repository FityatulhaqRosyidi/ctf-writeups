# Bytes_and_Big_Integer (10 pts)
crypto

## Deskripsi
> Convert the following integer back into a message:
> ``` console
> 11515195063862318899931685488813747395775516287289682636499965282714637259206269
> ```

## Solusi
diberikan bilangan bulat besar (big integer), kita diminta merubahnya ke representasi bytes nya

untuk hal ini, gunakan fungsi `long_to_bytes()` pada library `pycryptodome`

``` python
from Crypto.Util.number import long_to_bytes

ct = 11515195063862318899931685488813747395775516287289682636499965282714637259206269
pt = long_to_bytes(ct)
print(pt)
```

