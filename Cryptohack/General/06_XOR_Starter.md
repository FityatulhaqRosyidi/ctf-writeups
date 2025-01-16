# XOR Starter (10 pts)
crypto

## Dekripsi
> Given the string ```label```, XOR each character with the integer ```13```. Convert these integers back to a string and submit the flag as ```crypto{new_string}```.

## Solusi
challenge ini cukup sederhana, kita hanya perlu xor tiap karakter di ```label``` dengan angka 13.

``` python
from pwn import xor

pt = xor('label', 13).decode()
pt = ''.join(['crypto{', pt, '}'])
print(pt)
```
