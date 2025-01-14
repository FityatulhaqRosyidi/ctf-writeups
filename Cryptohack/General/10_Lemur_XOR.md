# Lemur XOR (40 pts)
crypto

## Deskripsi
> I've hidden two cool images by XOR with the same secret key so you can't see them!
>
> [lemur.png](https://cryptohack.org/static/challenges/lemur_ed66878c338e662d3473f0d98eedbd0d.png)
> [flag.png](https://cryptohack.org/static/challenges/flag_7ae18c704272532658c10b5faad06d74.png)

## Solusi
diberikan dua gambar yang sudah di XOR dengan kunci yang sama. secara matematis, jika kita xor kembali dua gambar tersebut, image key akan saling 
menghilangkan karena key ^ key = 0 sehingga hanya tersisa hasil xor gambar lemur dan flag. 

berikut contoh script python untuk permasalahan diatas
``` python
from PIL import Image
from pwn import xor

lemur = Image.open("lemur.png")
flag = Image.open("flag.png")

leak_bytes = xor(lemur.tobytes(), flag.tobytes())
leak = Image.frombytes(flag.mode, flag.size, leak_bytes)

leak.save('leak.png')
```
pada gambar leak.png, didapat flag 
``` console
crypto{XORly_not!}
```



