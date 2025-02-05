menampilkan semua bilangan prima dibawah $N$       

``` python 
def sieveOfSundaram(n):
    primes = []
    nNew = int((n - 1) / 2);
    marked = [0] * (nNew + 1);

    for i in range(1, nNew + 1):
        j = i;
        while((i + j + 2 * i * j) <= nNew):
            marked[i + j + 2 * i * j] = 1;
            j += 1;

    if (n >= 2):
        primes.append(2)

    for i in range(1, nNew + 1):
        if (marked[i] == 0):
            primes.append(2 * i + 1)

    return primes

# n =

primes = sieveOfSundaram(n)
print(primes)
```
