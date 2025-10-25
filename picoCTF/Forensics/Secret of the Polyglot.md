# Secret of the Polyglot

## Challenge Description

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file here.

## Hints

This problem can be solved by just opening the file in different ways

## Solution

The file was a pdf when opened showed a string which seemed to be the last part of the flag. 

```bash
1n_pn9_&_pdf_53b741d6}
```

Guided by the hint, I changed the extension of the file from `pdf` to `png` and voilà I got the first part of the flag

<img width="50" height="50" alt="flag2of2-final" src="https://github.com/user-attachments/assets/88481ad1-1d1a-4e17-8258-db0d5af7b49d" />

Thus, the flag for this challenge is `picoCTF{f1u3n7_1n_pn9_&_pdf_53b741d6}`
