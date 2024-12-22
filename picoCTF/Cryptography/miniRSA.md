# miniRSA

## Challenge Descripption

Let's decrypt this: ciphertext? Something seems a bit small.

## Hints

- RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
- How could having too small an e affect the security of this 2048 bit key?
- Make sure you don't lose precision, the numbers are pretty big (besides the e value)

## Thought Process

Firstly I referred to the attached tutorial. And the I opened the ciphertext
```bash
N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125 
```
As the second hint suggests, ciphertext can be decrypted using the cube root attack. 
The cube root attack is a technique used in cryptography to exploit certain vulnerabilities in RSA encryption, specifically when the encryption exponent e=3 is used. In RSA encryption, a message `m` is raised to the power `e` (the encryption exponent) modulo a large number `N` (the public key) i.e, `c = m^e mod N` where c is the ciphertext. To decrypt, the receiver uses a private key to reverse the operation and recover m.
The cube root attack works when:
- The encryption exponent e is very small (e.g., e=3)
- The message m is small enough that `m^e < N`

## Solution 

To implement the attack I referred to [this](https://stackoverflow.com/questions/55436001/cube-root-of-a-very-large-number-using-only-math-library) and found the cube root of `c` as `13016382529449106065894479374027604750406953699090365388202874238148389207291005` using the following code
```bash
def find_invpow(x,n):
    """Finds the integer component of the n'th root of x,
    an integer such that y ** n <= x < (y + 1) ** n.
    """
    high = 1
    while high ** n < x:
        high *= 2
    low = high/2
    while low < high:
        mid = (low + high) // 2
        if low < mid and mid**n < x:
            low = mid
        elif high > mid and mid**n > x:
            high = mid
        else:
            return mid
    return mid + 1
```

Then I did the following conversions (decimal -> hex -> ASCII)

![image](https://github.com/user-attachments/assets/d13d33af-bafb-4c45-98f0-d5e392d61312)
![image](https://github.com/user-attachments/assets/6d27ffca-c627-48ef-b077-8d0497d06978)

Thus the flag for this challenge is picoCTF{n33d_a_lArg3r_e_606ce004}

