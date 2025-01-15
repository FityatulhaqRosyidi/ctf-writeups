# ASCII (5 pts)
Crypto

## Deskripsi
> ASCII is a 7-bit encoding standard which allows the representation of text using the integers 0-127.
> Using the below integer array, convert the numbers to their corresponding ASCII characters to obtain a flag.
> 
> ``` console
> [99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110, 116, 52, 98, 108, 51, 125]
> ```


## Solusi
Kita diminta untuk meng-convert angka2 di atas ke representasi karakter ascii nya. 
Agar lebih mudah dan efisien, gunakan program python untuk solve challenge ini.
Untuk convert integer ke representasi karakter ascii nya, di python dapat digunakan fungsi ```chr()```, 
sedangkan untuk sebaliknya, dapat digunakan fungsi ```ord()```.

tabel ASCII dapat dilihat [disini](https://www.rapidtables.com/code/text/ascii-table.html)

```python 
ct = [99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110, 116, 52, 98, 108, 51, 125]
pt = ""
for i in ct:
  pt += chr(i)
print(pt)
```




