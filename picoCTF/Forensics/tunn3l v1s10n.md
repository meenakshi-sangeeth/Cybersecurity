# tunn3l v1s10n

## Challenge Description

We found this file. Recover the flag.

## Hints

Weird that it won't display right...

## Thought Process

I opened the attached file and it contained "BM" followed by characters that didn't make any sense. On Googling, I figured out that the donwloaded file is actually a bitmap image file. The "BM" at the start is part of the file header and indicates the file is in the BMP format. So I changed the extension of the file to bmp but alas that wasn't fruitful. I was clueless as to how to proceed so I referred to [this](https://trailofbits.github.io/ctf/forensics/). I figured I might have to perform hex analysis and thus I uploaded the image to an [online hex editor](https://hexed.it/) 

![image](https://github.com/user-attachments/assets/1782d36b-222d-4720-be3b-75f4d9c543cb)

## Solution

To know if the current file is in the correct format or not I have to compare it with the right one and for that I Googled and found [this](https://en.wikipedia.org/wiki/BMP_file_format) 

![image](https://github.com/user-attachments/assets/fecacc2e-2ed7-4941-9e25-5eac54e5a80c)

As you can see in the DIB header the four bytes are for the number of bytes in the DIB header however we cannot see any numerical value in the format of our image. So I changed it into the number of bytes like it is provided in the Wikipedia and that gave me the folowing image

![image](https://github.com/user-attachments/assets/902b941e-f4fa-4481-ab72-ebd80e59128a)

Now this image felt like it was being cropped so I tried changing the dimensions

![image](https://github.com/user-attachments/assets/ac8deadb-9ff4-48ca-a38d-ff8d7d578ce5)

This gave me the following image

![image](https://github.com/user-attachments/assets/7d5d8aa3-5cc2-44c4-a63f-67f18c0de4ea)

Thus the flag for this challenge is picoCTF{qu1t3_a_v13w_2020}



