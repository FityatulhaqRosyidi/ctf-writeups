# Privacy-Enhanced Mail? (25 pts)
crypto

## Deskripsi
> As we've seen in the encoding section, cryptography involves dealing with data in a wide variety of formats: big integers, raw bytes, hex strings and more. A few structured formats have been standardised to help send and receive cryptographic data. It helps to be able to recognise and manipulate these common data formats.
>
> PEM is a popular format for sending keys, certificates, and other cryptographic material. It looks like:
> ``` console
> -----BEGIN RSA PUBLIC KEY-----
> MIIBCgKC... (a whole bunch of base64)
> -----END RSA PUBLIC KEY-----
> ```
> It wraps base64-encoded data by a one-line header and footer to indicate how to parse the data within. Perhaps unexpectedly, it's important for there to be the correct number of hyphens in the header and footer, otherwise cryptographic tools won't be able to recognise the file.
>
> The data that gets base64-encoded is DER-encoded ASN.1 values. Confused? The resources linked below have more information about what these acronyms mean but the complexity is there for historical reasons and going too deep into the details may drive you insane.
>
> Extract the private key d as a decimal integer from [this](https://cryptohack.org/static/challenges/privacy_enhanced_mail_1f696c053d76a78c2c531bb013a92d4a.pem) PEM-formatted RSA key.

resource :
- [ASN.1 vs DER vs PEM vs x509 vs PKCS#7 vs ....](https://www.cryptologie.net/article/260/asn1-vs-der-vs-pem-vs-x509-vs-pkcs7-vs/)
- [A Warm Welcome to ASN.1 and DER](https://letsencrypt.org/docs/a-warm-welcome-to-asn1-and-der/)


## Solusi
Diberikan sebuah file kunci dengan format PEM. kita diminta mengekstrak private key $d$ dari file tersebut.
kita dapat memanfaatkan fungsi ```RSA.importKey``` dari library ```pycryptodome``` untuk mengekstrak kunci dari file berformat PEM.

``` python
from Crypto.PublicKey import RSA

f = open('privkey.pem', 'r')
key = RSA.importKey(f.read())

print(key.d)
```


