# EVEN RSA CAN BE BROKEN???

## Challenge Description

This service provides you an encrypted flag. Can you decrypt it with just N & e?
Connect to the program with netcat:
$ nc verbal-sleep.picoctf.net 60565
The program's source code can be downloaded here.

## Hints

1. How much do we trust randomness?  
2. Notice anything interesting about N? 
3. Try comparing N across multiple requests 

## Solution

I was given the values of `C`, `e`, and `n`. Normally, with RSA, you need the private key `d` to decrypt the message using the formula
```bash
M = C^d mod n
```

But the challenge didn’t give `d`, so I knew I had to somehow calculate it myself.
The only way to do that is to find `ϕ(n)`, which you can only compute if you know the prime factors of `n`. That led me to inspect the value of `n` more carefully. And well it's clearly visible that n is an even number thus divisible by 2 i.e, `n = 2*p`
Now that’s a huge red flag because normally `n` is the product of two large primes. So if one of them is just 2, it's ridiculously easy to factor making the encryption weak. Since `n = 2 × p`, I immediately got the prime `p` by just dividing `n` by 2 
`p = n // 2`

To calculate the totient `ϕ(n)`, which is used to compute the private key
```bash
ϕ(n) = (2 - 1)(p - 1) = p - 1
```

Using Python’s pow() function with 3 arguments, I found the modular inverse of e modulo ϕ(n)
```bash
d = pow(e, -1, p - 1)
```

Then I decrypted C using
```bash
M = pow(C, d, n)
```

RSA encryption turns messages into large numbers, so I had to convert M back into readable text. I had some trouble in the conversion so I had to refer to [this](https://pythonhosted.org/pycrypto/Crypto.Util.number-module.html)
```bash
from Crypto.Util.number import long_to_bytes
flag = long_to_bytes(M)
```

Thus the flag for this challenge is `picoCTF{tw0_1$_pr!m3f81fef0a}`
