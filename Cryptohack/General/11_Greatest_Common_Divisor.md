# Greatest Common Divisor (15 pts)
crypto

## Deskripsi
> calculate gcd(66528,52920) and enter it below


## Solusi
Sebenarnya ini lebih ke challenge matematik, kita diminta mencari hasil dari gcd(66528,52920), banyak web untuk solve soal ini,
namun lebih baik jika kita solve dengan program python sebagai latihan.

``` python
def gcd(a, b):
    return gcd(b%a, a) if a else b

print(gcd(66528,52920))
```
hasilnya ```1512```
