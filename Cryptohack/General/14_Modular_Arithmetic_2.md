# Modular Arithmetic 2 (20 pts)
crypto

## Deskripsi
>  Calculate :
> 
> $$273246787654^{65536} \bmod 65537$$


## Solusi
Kita diminta mengitung hasil dari 

$$273246787654^{65536} \bmod 65537$$

perhitungannya cukup sederhana. karena nilai modulusnya ```655537```  adalah bilangan prima, kita dapat
menggunakan teorema [little fermat](https://en.wikipedia.org/wiki/Fermat%27s_little_theorem).

untuk sembarang bilangan bulat a, dan bilangan prima p, berlaku

$$ a^{p-1} \equiv 1 \bmod p $$

jadi, hasilnya adalah ```1```.


