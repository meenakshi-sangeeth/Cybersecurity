# Ph4nt0m 1ntrud3r

## Challenge Description

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.
To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!
Find the PCAP file here Network Traffic PCAP file and try to get the flag.

## Hints

1. Filter your packets to narrow down your search. 
2. Attacks were done in timely manner. 
3. Time is essential 

## Solution

I opened the file in Wireshark and went through the packets to see if there's anything unusual. And I came across `==` in multiple packets which is a common signature for Base64-encoded data. 
![image](https://github.com/user-attachments/assets/3ba81fcb-3820-4cef-b936-a1ab83c2e02a)

So I searched for all the packets which cointained `==` using `Ctrl+F` and decoded those strings using an [online converter](https://www.base64decode.org/)

![image](https://github.com/user-attachments/assets/375fff92-2747-426a-bce5-669e9bdd9a51)

![image](https://github.com/user-attachments/assets/ec54408a-b488-405b-b4c2-1a9bbf2807fc)

![image](https://github.com/user-attachments/assets/e1da5599-6d4a-4f2d-b484-54038a37c516)

![image](https://github.com/user-attachments/assets/de11c432-465a-4d03-bcde-a5186010be3f)

![image](https://github.com/user-attachments/assets/57cb7b1e-d798-4e14-81a0-88baa390b07b)

![image](https://github.com/user-attachments/assets/b987c51a-5cbc-4f68-8cf1-1a41b3ecf91b)

![image](https://github.com/user-attachments/assets/ae9efc03-7da4-41de-8a65-96078095bb9f)

Thus the flag for this challenge is `picoCTF{1t_w4snt_th4t_34sy_tbh_4r_af160980}`
