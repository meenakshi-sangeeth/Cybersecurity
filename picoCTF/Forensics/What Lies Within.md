# What Lies Within

## Challenge Description

There's something in the building. Can you retrieve the flag?

## Hint

There is data encoded somewhere... there might be an online decoder.

## Solution

After a lot of attempts using `exiftool`,`strings`, online forensic tools, I used `zsteg` which is a tool designed to analyze images (specifically PNG and BMP formats) for hidden data using various steganographic techniques

```bash
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads#  zsteg  buildings.png
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"
```

Thus the flag for this challenge is `picoCTF{h1d1ng_1n_th3_b1t5}`
