# Irish-Name-Repo 3

## Challenge Description

There is a secure website running at https://jupiter.challenges.picoctf.org/problem/40742/ (link) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Hint

Seems like the password is encrypted.  

## Solution

I opened the attached website and went to the admin login page

![image](https://github.com/user-attachments/assets/96a2c904-aa85-4ad9-8bf1-c4e4aee2709a)

![image](https://github.com/user-attachments/assets/58b56b7e-678f-455f-9440-7c963475413c)

I entered a random password which just showed "Login Failed" as expected. I tried the classic SQL Injection payload which also wasn't fruitful. Then I inspected the page source and found something interesting

![image](https://github.com/user-attachments/assets/64cf1664-e800-466e-af10-c6c3373af2b4)

Upon some googling, I found out that `debug` is often used to toggle internal output in dev or debug environments. So I tried changed the value from 0 to 1 and resubmitted the form with the SQL injection. This time, instead of an error, I got the following result

![image](https://github.com/user-attachments/assets/5404b1ac-2c2c-4dc5-b076-9ef0ac172b6b)

I noticed that the letters 'o' and 'r' had been changed to 'b' and 'e' in the query string which looked odd. To investigate further, I entered `' or 1=1--abcdefghijklmnopqrstuvwxyz` which gave the following result

![image](https://github.com/user-attachments/assets/d81eaa0c-98fa-41f0-bc09-a8c4962c4d5d)

It was clear now that all alphabetical characters were being shifted 13 positions forward in the alphabet which means that ROT13 Caesar cipher was being applied to the input. So in order to inject anything meaningful, I just have to encode it using ROT13. Thus I gave `' be 1=1--` as input which gave me the flag

![image](https://github.com/user-attachments/assets/c6b1449c-a343-4f30-bc98-94c485eb502b)

Thus the flag for this challenge is `picoCTF{3v3n_m0r3_SQL_4424e7af}`
