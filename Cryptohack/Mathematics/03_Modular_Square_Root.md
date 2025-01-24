# Modular Square Root (35 pts)
crypto

## Deskripsi
> Find the square root of a modulo the 2048-bit prime p. Give the smaller of the two roots as your answer.
> 
> Challenge:
> - [output.txt](https://cryptohack.org/static/challenges/output_abe0beb359a950c8a0a9300897528a9d.txt)

## Solusi
Diberikan bilangan bulat besar a dan p. Kita diminta mencari akar kuadrat a modulo p. asumsikan a adalah quadratic residue.

untuk challenge ini, kita bisa menggunakan algoritma Tonelli-Shanks untuk mencari akar kuadrat modular. 
<br>namun karena 𝗌̶𝖺̶𝗒̶𝖺̶ ̶𝗆̶𝖺̶𝗅̶𝖺̶𝗌̶ algoritmanya agak ribet, kita bisa menggunakan fungsi `sqrt_mod` yang telah disediakan oleh library `sympy`.
``` python
from sympy import sqrt_mod
# a = 
# p = 
print(sqrt_mod(a, p))
```

ingat kata pepatah, "Orang cerdas bikin fungsi sendiri, orang bijak pke fungsi libary".

