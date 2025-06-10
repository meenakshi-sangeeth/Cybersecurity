# Mob psycho

## Challenge Description

Can you handle APKs?
Download the android apk here.

## Hints

1. Did you know you can unzip APK files? 
2. Now you have the whole host of shell tools for searching these files. 


## Solution

Guided by the hints, I first unzipped the attached apk file

![image](https://github.com/user-attachments/assets/eb5d0b54-d769-4592-b693-8fea805f584e)

Now, I'll have to search for the flag within these folders which have number of folders and files inside. My first instinct was to search for "flag" in the search barWoahhh that was easy! I opened the file and got the following string

![image](https://github.com/user-attachments/assets/76644d1e-efe9-40fd-8796-bedcb3bbc3ad)

```bash
7069636f4354467b6178386d433052553676655f4e5838356c346178386d436c5f62313132616535377d
```

Now all I've to do is convert the hex to ASCII, for which I used an [online tool](https://www.rapidtables.com/convert/number/hex-to-ascii.html)

![image](https://github.com/user-attachments/assets/3e218cd5-3315-45f7-8b31-c8bc505c29c0)

Thus the flag for this challenge is `picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_b112ae57} `



