# Base64
crypto

## Deskripsi
> Another common encoding scheme is Base64, which allows us to represent binary data as an ASCII string using an alphabet of 64 characters. One character of a Base64 string encodes 6 binary digits (bits), and so 4 characters of Base64 encode three 8-bit bytes.
>
> Base64 is most commonly used online, so binary data such as images can be easily included into HTML or CSS files.
>
> Take the below hex string, decode it into bytes and then encode it into Base64.
> ``` console
> 72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf
> ```

## Solusi
diberikan hex, kita diminta untuk decode hex tersebut ke bentuk bytes kemudian encode ke bentuk base64

di python, encoding base64 dapat menggunakan library base64

``` python
import base64

ct = "72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf"
ct = bytes.fromhex(ct)
pt = base64.b64encode(ct).decode()
print(pt)
```
hasil :
``` console
crypto/Base+64+Encoding+is+Web+Safe/
```
