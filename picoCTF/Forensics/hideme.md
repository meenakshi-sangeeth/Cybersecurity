# hideme

## Challenge Description

Every file gets a flag.
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye here.

## Solution

Following is the attached file

![image](https://github.com/user-attachments/assets/b339fb98-f727-4c36-9b59-b7f110be6914)


```bash
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads#  binwalk flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2959, uncompressed size: 3108, name: secret/flag.png
42998         0xA7F6          End of Zip archive, footer length: 22

root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# sudo binwalk -e --run-as=root flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2959, uncompressed size: 3108, name: secret/flag.png
42998         0xA7F6          End of Zip archive, footer length: 22
```
I opened the extracted file

![image](https://github.com/user-attachments/assets/3db2fc60-1d1a-4555-b302-f91f6b2fbaf3)
![image](https://github.com/user-attachments/assets/2cfc7a44-f02e-419b-b678-932980834bc3)

On opening the `secret` file, I got the following image

![image](https://github.com/user-attachments/assets/3d66c0f6-f5dd-4422-b524-5597601316c7)

Thus the flag for this challenge is `picoCTF{Hiddinng_An_imag3_within_@n_ima9e_dc2ab58f}`
