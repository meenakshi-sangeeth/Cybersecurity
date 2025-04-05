# Pixelated

## Challenge Description

I have these 2 images, can you make a flag out of them? scrambled1.png scrambled2.png

## Hints

1. https://en.wikipedia.org/wiki/Visual_cryptography
2. Think of different ways you can "stack" images

## Solution

![scrambled1](https://github.com/user-attachments/assets/848007e8-b759-44a4-b406-7b71ad91be69)

![scrambled2](https://github.com/user-attachments/assets/ce25a37a-f7ae-46fe-afb6-84fbda7ffa17)

From the hints, I came to the comclusion that I'll have to blend the two images to get the original image which might lead me to the flag. For that I referred to [this](https://www.tutorialspoint.com/python_pillow/python_pillow_image_blending.htm) and used the following code

```bash
from PIL import Image

# Load two images
image1 = Image.open("scrambled1.png")
image2 = Image.open("scrambled2.png")

# Blend the images with alpha = 0.5
result = Image.blend(image1, image2, alpha=0.5)

# Display the input and resultant iamges
result.show()
```

I got the original image

![combined_image](https://github.com/user-attachments/assets/cf818ec8-b8d7-4432-ab11-e1967685f850)

Since the flag is not visible in plain sight I used an [online steganography tool](https://georgeom.net/StegOnline/image) and played with the options until it gave me the flag

![image](https://github.com/user-attachments/assets/23fe5495-1480-4ed9-a857-27e621eca7bd)

Thus the flag for this challenge is `picoCTF{7188864c}`
