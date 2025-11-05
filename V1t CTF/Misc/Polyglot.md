## Challenge

Look, read, and most importantly, WATCH the duck!

File can only open in Windows

Polyglot.png

## Solution

The challenge name "Polyglot" suggested the file is valid in multiple formats. So first I changed the file extension to `.mp4` since the challenge said "WATCH the duck". On playing, the video showed `Password is HideTheDuck123@`

Then I tried using `zteg`, didn't work and then `7z` which gave me the flag

```bash
7z x polyglot.png -pHideTheDuck123@
7-Zip [64] 16.02 : Copyright (c) 1999-2016 Igor Pavlov : 2016-05-21
p7zip Version 16.02 (locale=C.UTF-8,Utf16=on,HugeFiles=on,64 bits,8 CPUs 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz (806C1),ASM,AES-NI)
Scanning the drive for archives:
1 file, 6300910 bytes (6154 KiB)
Extracting archive: polyglot.png
--
Path = polyglot.png
Type = zip
Physical Size = 6300910
Embedded Stub Size = 6158648
Everything is Ok
Size:       160694
Compressed: 6300910
```

Insdie the zip file there was an image which alas was not the flag. Since it was of the format `jpg`, I used `steghide`

```bash
steghide extract -sf angri.jpg -p HideTheDuck123@
wrote extracted data to "flag.txt".
```

Inside the `txt` file was the flag

Flag: `v1t{duck_l0v3_w4tch1ng_p2r3}`


