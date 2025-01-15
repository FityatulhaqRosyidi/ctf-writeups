# Network Attacks (5 pts)
crypto

## Deskripsi
> Several of the challenges are dynamic and require you to talk to our challenge servers over the network. This allows you to perform man-in-the-middle attacks on people trying to communicate, or directly attack a vulnerable service. To keep things consistent, our interactive servers always send and receive JSON objects.
>
> Such network communication can be made easy in Python with the ```pwntools``` module. This is not part of the Python standard library, so needs to be installed with pip using the command line ```pip install pwntools```.
>
> For this challenge, connect to ```socket.cryptohack.org``` on port ```11112```. Send a JSON object with the key ```buy``` and value ```flag```.

## Solusi
Pada Challenge ini, kita diminta mengirim sebuah payload ke server.
payload dengan format json dengan key ```buy``` dan value ```flag```.

``` python
from json import dumps, loads
from pwn import remote

io = remote('socket.cryptohack.org', 11112)

print(io.recvline())
print(io.recvline())
print(io.recvline())
print(io.recvline())
payload = {'buy' : 'flag'}
io.sendline(dumps(payload).encode())
print(loads(io.recvline().decode()))
```
hasil :
``` console
{'flag': 'crypto{sh0pp1ng_f0r_fl4g5}'}
```
