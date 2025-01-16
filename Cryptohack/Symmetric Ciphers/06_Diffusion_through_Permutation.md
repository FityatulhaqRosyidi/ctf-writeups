# Diffusion through Permutation (30 pts)
crypto

## Deskripsi
> We've provided code to perform MixColumns and the forward ShiftRows operation. After implementing ```inv_shift_rows```, 
take the state, run ```inv_mix_columns``` on it, then ```inv_shift_rows```, convert to bytes and you will have your flag.
>
> [chall.py](https://cryptohack.org/static/challenges/diffusion_ee6215282094b4ae8cd1b20697477712.py)

## Solusi
Kita diminta untuk menyempurnakan fungsi ```inv_shift_rows```. kemudian menggunakan fungsi tersebut bersama dengan ```inv_mix_columns``` untuk memperoleh flag.

pertama kita sempurnakan  ```inv_shift_rows```.
``` python
def inv_shift_rows(s):
    s[1][1], s[2][1], s[3][1], s[0][1] = s[0][1], s[1][1], s[2][1], s[3][1]
    s[2][2], s[3][2], s[0][2], s[1][2] = s[0][2], s[1][2], s[2][2], s[3][2]
    s[3][3], s[0][3], s[1][3], s[2][3] = s[0][3], s[1][3], s[2][3], s[3][3]

```

kemudian untuk memperoleh flag, state matrix kita proses dengan urutan seperti berikut
``` python
inv_mix_columns(state)
inv_shift_rows(state)
print(matrix2bytes(state))
```
