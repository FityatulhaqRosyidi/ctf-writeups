# Manyprime (40 pts)
crypto
## Deskripsi
> Using one prime factor was definitely a bad idea so I'll try using over 30 instead.
>
> Challenge:
> - [output.txt](https://cryptohack.org/static/challenges/output_5a478a5d4764257d0bbdfaed340fcbdd.txt)

## Solusi
Diberikan n, e, dan ct. kita diminta mendekripsi ct. 
diketahui pada soal bahwa n dibentuk dari 30 lebih bilangan prima.

faktor-faktor n dapat dengan mudah diperoleh dengan memanfaatkan factordb.com.
kemudian untuk memperoleh phi, setiap faktor di kurangi 1, kemudian saling dikalikan.

berikut adalah contoh script solvernya
``` python
# solver.py
from Crypto.Util.number import inverse, long_to_bytes

# n, e, ct = {REDACTED}

p1 = 9282105380008121879
p2 = 9303850685953812323
p3 = 9389357739583927789
p4 = 10336650220878499841
p5 = 10638241655447339831
p6 = 11282698189561966721
p7 = 11328768673634243077
p8 = 11403460639036243901
p9 = 11473665579512371723
p10 = 11492065299277279799
p11 = 11530534813954192171
p12 = 11665347949879312361
p13 = 12132158321859677597
p14 = 12834461276877415051
p15 = 12955403765595949597
p16 = 12973972336777979701
p17 = 13099895578757581201
p18 = 13572286589428162097
p19 = 14100640260554622013
p20 = 14178869592193599187
p21 = 14278240802299816541
p22 = 14523070016044624039
p23 = 14963354250199553339
p24 = 15364597561881860737
p25 = 15669758663523555763
p26 = 15824122791679574573
p27 = 15998365463074268941
p28 = 16656402470578844539
p29 = 16898740504023346457
p30 = 17138336856793050757
p31 = 17174065872156629921
p32 = 17281246625998849649

phi = 1
for i in (p1,p2,p3,p4,p5,p6,p7,p8,p9,p10,p11,p12,p13,p14,p15,p16,p17,p18,p19,p20,p21,p22,p23,p24,p25,p26,p27,p28,p29,p30,p31,p32):
    phi *= (i - 1)


d = inverse(e, phi)
pt = pow(ct, d, n)
decrypted = long_to_bytes(pt).decode()
print(decrypted)
```
