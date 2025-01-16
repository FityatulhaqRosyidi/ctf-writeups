# Flipping Bits
crypto

## Deskripsi
> Disabling C2 requires cracking a RSA message. You have [two ciphertexts](https://blockctf.com/2018/flipping_bits.tar.gz).
> The public key is (e1, n).
>
> Fortunately (this time), space rabiation caused some bit flibs and the second ciphertext was encrypted with a faulty public key (e2, n). Can you recover the plaintexts?

## Solusi
Diberikan ct1, ct2, e1, e2, m dan n.
``` console
ct1:  13981765388145083997703333682243956434148306954774120760845671024723583618341148528952063316653588928138430524040717841543528568326674293677228449651281422762216853098529425814740156575513620513245005576508982103360592761380293006244528169193632346512170599896471850340765607466109228426538780591853882736654
ct2:  79459949016924442856959059325390894723232586275925931898929445938338123216278271333902062872565058205136627757713051954083968874644581902371182266588247653857616029881453100387797111559677392017415298580136496204898016797180386402171968931958365160589774450964944023720256848731202333789801071962338635072065
e1:  13
e2:  15
modulus:  103109065902334620226101162008793963504256027939117020091876799039690801944735604259018655534860183205031069083254290258577291605287053538752280231959857465853228851714786887294961873006234153079187216285516823832102424110934062954272346111907571393964363630079343598511602013316604641904852018969178919051627
```
disini kita punya dua eksponen yang berbeda, namun m dan n sama. persoalan ini dapat dipecahkan dengan konsep rsa multi exponen. 

dapat dibentuk dua persamaan

$$ ct_1 = m^{e_1} \bmod n $$
$$ ct_2 = m^{e_2} \bmod n $$

$m$ bisa kita dapatkan dengan persamaan

$$ m = ct_1^a \cdot ct_2^b \bmod n $$

dimana $a, b$ memenuhi

$$ ae_1 + be_2 = gcd(e_1,e_2) $$

pertama, kita cari $a, b$ dengan menggunakan ```extended euclidian algorithm```
``` python
def egcd(a, b) :
    if a == 0:
        return b, 0, 1
    else :
        gcd, x, y = egcd(b % a, a)
        return gcd, y - (b // a) * x, x

_, a, b = egcd(e1, e2)
```
kemudian hitung dengan persamaan sebelumnya untuk mencari $m$
``` python
from Crypto.Util.number import long_to_bytes

m = pow(pow(ct1,a,n) * pow(ct2,b,n) , 1, n)

m = long_to_bytes(m).decode()
print(m)
```
hasil :
``` console
flag-54d3db5c1efcd7afa579c37bcb560ae0
```


