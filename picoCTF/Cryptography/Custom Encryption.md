# Custom Encryption

## Challenge Description

## Thought Process

Given below is the attached file content followed by the encryption
```bash
a = 89
b = 27
cipher is: [33588, 276168, 261240, 302292, 343344, 328416, 242580, 85836, 82104, 156744, 0, 309756, 78372, 18660, 253776, 0, 82104, 320952, 3732, 231384, 89568, 100764, 22392, 22392, 63444, 22392, 97032, 190332, 119424, 182868, 97032, 26124, 44784, 63444]

```
```bash
from random import randint
import sys


def generator(g, x, p):
    return pow(g, x) % p


def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher


def is_prime(p):
    v = 0
    for i in range(2, p + 1):
        if p % i == 0:
            v = v + 1
    if v > 1:
        return False
    else:
        return True


def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text


def test(plain_text, text_key):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    a = randint(p-10, p)
    b = randint(g-10, g)
    print(f"a = {a}")
    print(f"b = {b}")
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
    semi_cipher = dynamic_xor_encrypt(plain_text, text_key)
    cipher = encrypt(semi_cipher, shared_key)
    print(f'cipher is: {cipher}')


if __name__ == "__main__":
    message = sys.argv[1]
    test(message, "trudeau")

```
To decode the flag, I'll have to reverse the encryption process. The code uses modular exponentiation along with a dynamic XOR encryption method to secure the plaintext.
So first I'll reverse the dynamic XOR encryption to retrieve the intermediate ciphertext. Then I'll reverse the modular exponentiation to recover the original ciphertext.
And finally convert the decrypted ciphertext back to characters using ASCII values

## Solution

```bash
from sympy import mod_inverse

# Dynamic XOR decryption function
def dynamic_xor_decrypt(cipher_text, text_key):
    decrypted_text = ""
    key_length = len(text_key)
    for i, char in enumerate(cipher_text):
        key_char = text_key[i % key_length]
        decrypted_char = chr(ord(char) ^ ord(key_char))
        decrypted_text += decrypted_char
    return decrypted_text

# Reverse the modular exponentiation to obtain the original ciphertext
def reverse_generator(g, x, p):
    return pow(g, x, p)

# Decrypt function to reverse the encryption process
def decrypt(cipher, key):
    decrypted_text = ""
    for num in cipher:
        decrypted_num = num // (key*311)  # Reversing the encryption operation
        decrypted_text += chr(decrypted_num)
    return decrypted_text

# Constants from the provided information
a = 89
b = 27
enc_flag = [33588, 276168, 261240, 302292, 343344, 328416, 242580, 85836, 82104, 156744, 0, 309756, 78372, 18660, 253776, 0, 82104, 320952, 3732, 231384, 89568, 100764, 22392, 22392, 63444, 22392, 97032, 190332, 119424, 182868, 97032, 26124, 44784, 63444]
p = 97
g = 31

# Reverse modular exponentiation to obtain shared key
u = reverse_generator(g, a, p)
v = reverse_generator(g, b, p)
shared_key = reverse_generator(v, a, p)

# Decrypt intermediate ciphertext
intermediate_ciphertext = decrypt(enc_flag, shared_key)

# Reverse dynamic XOR encryption
flag = dynamic_xor_decrypt(intermediate_ciphertext, "trudeau")

print("Decoded Flag:", flag)
```

The above code gave me the flag as }835994cd_d6tp0rc2d_motsuc{FTCocip. On reversing it, I got the flag for this challenge "picoCTF{custom_d2cr0pt6d_dc499538}"
