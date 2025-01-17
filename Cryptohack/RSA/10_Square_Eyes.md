# Square Eyes (35 pts)
crypto

## Deskripsi
> It was taking forever to get a 2048 bit prime, so I just generated one and used it twice.
>
> Challenge files: 
> - [output.txt](https://cryptohack.org/static/challenges/output_00dace150c0bc52f7abf03fc3e9529d2.txt)

## Solusi
Diberikan nilai n, e, dan ct. kita diminta mendekripsi ct dengan informasi yang tersedia. 
diketahui bahwa n dibentuk dari dua bilangan prima besar yang sama. sebut saja $P$. <br>
artinya, $n = p^2$

rumus tuotient euler untuk bilangan prima berpangkat :

$$ \phi(p^k) = p^{k-1}(p-1) $$
