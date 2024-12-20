# Trivial Flag Transfer Protocol

## Challenge Description

Figure out how they moved the flag.

## Hint

What are some other ways to hide data?

## Thought Process

I donwloaded the attached file and found that it was pcapng file. Now I had no idea what a pcapng file is or how to analyse it. So I did some research and I found out that pcapng file (Packet Capture Next Generation file) is basically a file format that stores captured network traffic data. Think of it like a "recording" of all the messages sent and received over a network during a specific time.It helps analyze network activity to find problems, understand how data moves, or uncover hidden information (like in CTF challenges).
Wireshark is a free and widely used ool that lets you see all the messages (called "packets") being sent and received over a network. Thus wireshark can be used to filter and inspect the packets in the given pcapng file. I donwloaded wireshark and opened the file in it
![image](https://github.com/user-attachments/assets/691f9783-012b-405f-8081-8628850c948a)

As you can see most of the network traffic here are TFTP. I did some research on TFTP as well and this is what I got to know. TFTP (Trivial File Transfer Protocol) is a file transfer protocol without the need of authentication and data encryption making it "trivial". It’s fast and easy to use but not secure. 

So now knowing what TFTP is, I filtered the traffic to see what were sent and received
![image](https://github.com/user-attachments/assets/52506f47-a261-4bb7-91ca-f5316cd5d95d)

The transferred files are “instructions.txt”, “plan”, "program.deb", “picture1.bmp”, “picture2.bmp”, “picture3.bmp”. Now let’s export all of them by clicking File -> Export Object -> TFTP
![image](https://github.com/user-attachments/assets/bf51033d-ea04-4db7-b1d2-86e31d371d36)

I opened “instructions.txt” which contained the following string inside
```bash
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
```
It seemed like an encoded text so I tried different ciphers and ROT13 finally decoded the text as 
```bash
TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
```

So this led me to open the second file "plan" which contained another encoded string
```bash
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
```
I decoded it using ROT13 which gave the following text
```bash
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
```

## Solution

The flag is hidden in the image so now I had to checkout the photos with the help of `steghide`. For that I executed the following commands
```bash
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# steghide --help
steghide version 0.5.1

the first argument must be one of the following:
 embed, --embed          embed data
 extract, --extract      extract data
 info, --info            display information about a cover- or stego-file
   info <filename>       display information about <filename>
 encinfo, --encinfo      display a list of supported encryption algorithms
 version, --version      display version information
 license, --license      display steghide's license
 help, --help            display this usage information

embedding options:
 -ef, --embedfile        select file to be embedded
   -ef <filename>        embed the file <filename>
 -cf, --coverfile        select cover-file
   -cf <filename>        embed into the file <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to embed data
 -sf, --stegofile        select stego file
   -sf <filename>        write result to <filename> instead of cover-file
 -e, --encryption        select encryption parameters
   -e <a>[<m>]|<m>[<a>]  specify an encryption algorithm and/or mode
   -e none               do not encrypt data before embedding
 -z, --compress          compress data before embedding (default)
   -z <l>                 using level <l> (1 best speed...9 best compression)
 -Z, --dontcompress      do not compress data before embedding
 -K, --nochecksum        do not embed crc32 checksum of embedded data
 -N, --dontembedname     do not embed the name of the original file
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

extracting options:
 -sf, --stegofile        select stego file
   -sf <filename>        extract data from <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to extract data
 -xf, --extractfile      select file name for extracted data
   -xf <filename>        write the extracted data to <filename>
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

options for the info command:
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to get info about embedded data

To embed emb.txt in cvr.jpg: steghide embed -cf cvr.jpg -ef emb.txt
To extract embedded data from stg.jpg: steghide extract -sf stg.jpg
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# steghide extract -sf picturel.bmp
Enter passphrase:
steghide: could not open the file "picturel.bmp".
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# steghide extract-sf picturel.bmp -p DUEDILIGENCE
steghide: could not open the file "picturel.bmp".
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# steghide extract -sf picture2.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# steghide extract of picture3.bmpp DUEDILIGENCE
wrote extracted data to "flag.txt".
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# cat flag.txt
picoCTF{h1dd3n In pLaln 51GHT 18375919}
```

Thus the flag for this challenge is `picoCTF{h1dd3n In pLaln 51GHT 18375919}`


