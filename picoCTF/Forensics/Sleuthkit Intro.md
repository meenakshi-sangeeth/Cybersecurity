# Sleuthkit Intro

## Challenge Description

Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download disk image

## Solution

In digital forensics, the mmls command is a tool from the Sleuth Kit (TSK) that is used to display the layout of partitions on a storage device or image. It helps forensic investigators understand how a disk is organized and identify key partitions for analysis.

```bash
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# mmls disk.img
Error stat(ing) image file (raw_open: image "disk.img" - No such file or directory)
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# gunzip  disk.img.gz
root@MeenakshiSangeeth:/mnt/c/Users/Meenakshi Sangeeth/Downloads# mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

root@MeenakshiSangeeth:~# nc saturn.picoctf.net 56070
What is the size of the Linux partition in the given disk image?
Length in sectors: 0000202752
0000202752
Great work!
picoCTF{mm15_f7w!}
```
Thus the flag for this challenge is `picoCTF{mm15_f7w!}`
