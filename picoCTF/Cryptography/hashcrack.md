# hashcrack

## Challenge Description

A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?
Access the server using nc verbal-sleep.picoctf.net 53299

## Hint

1. Understanding hashes is very crucial. [Read more here.](https://primer.picoctf.org/#_hashing)
2. Can you identify the hash algorithm? Look carefully at the length and structure of each hash identified. 
3. Tried using any hash cracking tools? 

## Solution

Firstly I referred to the attached resource to get an idea about hashing. After going through it, I connected to the program

```bash
Welcome!! Looking For the Secret?

We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
Enter the password for identified hash:
```

As the hint suggested, I used to an [online tool](https://hashes.com/en/tools/hash_identifier) to identify the hash

![image](https://github.com/user-attachments/assets/3e6646d6-7653-4a0c-9bfe-5eaaa5edb98d)

Then I used an [online decoder](https://www.dcode.fr/md5-hash) to decode the hash

![image](https://github.com/user-attachments/assets/992585aa-a5c5-4f54-8ac4-24d8c01bfea5)

I entered the password and got the following output

```bash
Correct! You've cracked the MD5 hash with no secret found!

Flag is yet to be revealed!! Crack this hash: b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
Enter the password for the identified hash:
```
I repeated the same procedure

![image](https://github.com/user-attachments/assets/d5557855-9ab6-4fd2-bddd-92952a732b89)

![image](https://github.com/user-attachments/assets/1f52b9de-8a9c-4336-a829-fa59831245cf)

I entered the password which gave me an output similar to the previous one

```bash
Correct! You've cracked the SHA-1 hash with no secret found!

Almost there!! Crack this hash: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
Enter the password for the identified hash:
```
Once again I repeated the procedure

![image](https://github.com/user-attachments/assets/abdc5fd1-aa58-4fa2-a5a0-f1dfbacf5d52)

![image](https://github.com/user-attachments/assets/00071301-a166-472d-a117-c2782171245d)

```bash
Correct! You've cracked the SHA-256 hash with a secret found.
The flag is: picoCTF{UseStr0nG_h@shEs_&PaSswDs!_23622a7e}
```

Thus the flag for this challenge is `picoCTF{UseStr0nG_h@shEs_&PaSswDs!_23622a7e}`
