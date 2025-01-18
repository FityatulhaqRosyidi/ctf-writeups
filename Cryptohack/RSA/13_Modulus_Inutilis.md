# Modulus Inutilis (50 pts)
crypto

## Deskripsi
> My primes should be more than large enough now!
>
> Challenge:
> - [modulus_inutilis.py](https://cryptohack.org/static/challenges/modulus_inutilis_d2e0022b0165d99403eafeb0bea01231.py)
> - [output.txt](https://cryptohack.org/static/challenges/output_30cff153b7432055fc947fc5abdb57d3.txt)

## Solusi
Diberikan nilai n, e, dan ct. karena nilai e sangat kecil yaitu ```3```, dan n sangat besar, maka langsung saja dapat diasumsikan bahwa

$$ ct = m^3 $$
$$ m = \sqrt[3]{ct} $$

dengan sagemath, diperoleh akar pangkat 3 dari ct adalah ```624239975241694158443315202759206900318542905782320965248893```
``` python
from Crypto.Util.number import long_to_bytes

m = 624239975241694158443315202759206900318542905782320965248893
print(long_to_bytes(m))
```

