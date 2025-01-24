# Legendre Symbol (35 pts)
crypto

## Deksripsi
> Given the following 1024 bit prime and 10 integers, find the quadratic residue and then calculate its square root; the square root is your flag. Of the two possible roots, submit the larger one as your answer.
>
> Challenge files:
> - [output.txt](https://cryptohack.org/static/challenges/output_479698cde19aaa05d9e9dfca460f5443.txt)


## Solusi
Diberikan p dan list of integers. diantara list of integers terdapat satu quadratic residue. sebut saja $x$. kita diminta mencari akar kuadrat terkecil dari $x$ modulo p.

legendre symbol/euler criterion dapat digunakan untuk mengecek apakah suatu bilangan adalah quadratic residue atau bukan. untuk sembarang $p$ prima ganjil dan $a$ bilangan bulat relatif prima dengan $p$, maka berlaku :

$$ a^{p-1 \over 2} \equiv  \begin{cases}
   1 &\text{jika $a$ quadratic residue }  \\
   -1 &\text{jika $a$ non-quadratic residue} 
\end{cases}$$


``` python
from sympy import sqrt_mod
# p =
# ints = 
for a in ints:
    if (pow(a, (p - 1)//2, p) == 1):
        x = sqrt_mod(a, p)
        print(max(x, p - x))
```


