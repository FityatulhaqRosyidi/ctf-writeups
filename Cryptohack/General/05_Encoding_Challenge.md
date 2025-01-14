# Encoding Challenge (40 pts)
crypto

## Deskripsi
> Now you've got the hang of the various encodings you'll be encountering, let's have a look at automating it.
> Can you pass all 100 levels to get the flag?
> 
> Challenge files :
> 
> [13377.py](https://cryptohack.org/static/challenges/13377_86793614535c47dea371d2f0e406dbd9.py)
> 
> [pwntools_example.py](https://cryptohack.org/static/challenges/pwntools_example_f93ca6ccef2def755aa8f6d9aa6e9c5b.py)


## Solusi

diberikan sebuah program python yang berjalan di server, program tersebut melakukan looping beberapa kali untuk mengirim sebuah 
payload json yang berisi tipe enkripsi dan hasil enkripsi, contoh ```{'type' : ___, 'encoded': ___ }```.

setiap kali payload dikirim dari server, kita diminta mengirim payload serupa yang berisi hasil dekripsi payload sebelumnya, 
contoh ```{'decoded' : ___ }```.

jika jawaban salah, program berhenti. jika benar, program terus berlanjut hingga server mengirim payload yang berisi flag.

artinya, kita diminta membuat script yang dapat melakukan automasi pengiriman payload ke server hingga flag diberikan. berikut adalah 
salah satu contoh script solver python yang dapat menyelesaikan permasalahan diatas.

``` python
from pwn import remote
from json import loads, dumps
from base64 import b64decode
from codecs import encode
from Crypto.Util.number import long_to_bytes

io = remote('socket.cryptohack.org', 13377)

while 'flag' not in (encoded := loads(io.recvline().decode())):
    print(encoded)
    hsh = {"decoded": {
        'base64': lambda ct : b64decode(ct).decode(),
        'hex' : lambda ct : bytes.fromhex(ct).decode(),
        'rot13' : lambda ct : encode(ct, 'rot_13'),
        'bigint' : lambda ct : long_to_bytes(int(ct, 16)).decode(),
        'utf-8' : lambda ct : ''.join([chr(c) for c in ct])
    }[encoded['type']](encoded['encoded'])}
    io.sendline(dumps(hsh))

print(encoded['flag'])
```

hasil :
``` console
# python solve.py
crypto{3nc0d3_d3c0d3_3nc0d3}
```


