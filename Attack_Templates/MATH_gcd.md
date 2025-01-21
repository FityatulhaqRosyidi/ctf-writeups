Euclidean Algorithm 
```python
def egcd(a, b):
    if a == 0:
        return b, 0, 1
    else:
        gcd, x, y = egcd(b % a, a)
        return gcd, y - (b // a) * x, x

# a =
# b =

gcd, x, y = egcd(a, b)
```

<br>Extended Euclidean Algorithm 

``` python
def gcd(a, b):
    return gcd(b%a, a) if a else b

# a = 
# b =

x = gcd(a, b)
```
